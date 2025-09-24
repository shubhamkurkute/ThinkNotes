
#### Mix Path, Query and body parameters
We can mix Path, Query and request body parameter declarations freely and FastAPI will know what to do.
Body parameter is a parameter in a function which is created with the help of a Pydantic class.

```
from typing import Annotated

from fastapi import FastAPI, Path
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tax: float | None = None


@app.put("/items/{item_id}")
async def update_item(
    item_id: Annotated[int, Path(title="The ID of the item to get", ge=0, le=1000)],
    q: str | None = None,
    item: Item | None = None,
):
    results = {"item_id": item_id}
    if q:
        results.update({"q": q})
    if item:
        results.update({"item": item})
    return results
```

#### Multiple body Parameters
In the above example we declare only one body parameter where as we can also declare more than one.
```
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tax: float | None = None


class User(BaseModel):
    username: str
    full_name: str | None = None


@app.put("/items/{item_id}")
async def update_item(item_id: int, item: Item, user: User):
    results = {"item_id": item_id, "item": item, "user": user}
    return results
```

FastAPI will do the automatic conversion for the request, so the `item` parameter receives its specific content and the same for the `user`.
It will perform validation for the compound data.

#### Singular Values in Body
The same way there is query and path to define extra data for query and path parameters, FastAPI provides an equivalent body
For example from the above example you want to add a singular entity as a parameter besides the item and user. Then the FastAPI considers this as a query parameter, but you can instruct the FastAPI to treat it as a body using key  `body`.
```
from typing import Annotated

from fastapi import Body, FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tax: float | None = None


class User(BaseModel):
    username: str
    full_name: str | None = None


@app.put("/items/{item_id}")
async def update_item(
    item_id: int, item: Item, user: User, importance: Annotated[int, Body()]
):
    results = {"item_id": item_id, "item": item, "user": user, "importance": importance}
    return results
```

**Note: `Body`  also has all the same extra validation and metadata parameters as `Query`, `Path`  and others.**

#### Embed a single body parameter
Lets say you only have a single body parametet 'item'  from Pydantic model 'Item'. By default, fastapi will then expect its body directly. But if you want to expect a JSON  with a key 'item' and inside of it model contents, as it does when you declare extra body parameters, you can use the special Body parameter embed
`item: Item = Body (embed=True)` as in
`item: Annotated[Item, Body(embed=True)]`
