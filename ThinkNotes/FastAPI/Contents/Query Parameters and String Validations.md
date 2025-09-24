
FastAPI allows you to declare additional information and validation for your parameters.

Ex:
```
from fastapi import FastAPI

app = FastAPI()


@app.get("/items/")
async def read_items(q: str | None = None):
    results = {"items": [{"item_id": "Foo"}, {"item_id": "Bar"}]}
    if q:
        results.update({"q": q})
    return results
```

So we are going to enforce that even though "q" is optional, whenever it is provided, its length doesn't exceed 50 characters.
Here we use `Annotated` and `Query` library.

```
from typing import Annotated

from fastapi import FastAPI, Query

app = FastAPI()


@app.get("/items/")
async def read_items(q: Annotated[str | None, Query(max_length=50)] = None):
    results = {"items": [{"item_id": "Foo"}, {"item_id": "Bar"}]}
    if q:
        results.update({"q": q})
    return results
```

Here the query `q` can hold only 50 character, this is the extra validation we are adding.

#### Add more validations
You can add `min_length` before the `max_length` 

ex:
```
async def read_items(q:Annotated[str|None, Query(min_length = 3, max_length =100)] = None)
```

#### Add regular expressions
Can also add regex pattern in Query as a `pattern = "Some pattern"`
ex:
```
async def read_items(q:Annotated[str|None, Query(min_length = 3, max_length =100, pattern = ^fixedquery$)] = None)
```

#### Declare more Metadata
We can add more metadata about the parameter. Metadata means "data about the data", it tells the user about the data i.e. who made the data, time of data created, source of the data.
Ex:
```
from typing import Annotated

from fastapi import FastAPI, Query

app = FastAPI()


@app.get("/items/")
async def read_items(
    q: Annotated[
        str | None,
        Query(
            title="Query string",
            description="Query string for the items to search in the database that have a good match",
            min_length=3,
        ),
    ] = None,
):
    results = {"items": [{"item_id": "Foo"}, {"item_id": "Bar"}]}
    if q:
        results.update({"q": q})
    return results
```

#### Alias Parameters
Imageine that you want the parameter to be `item-query`. 
Like in:
`http://127.0.0.1:8000/items/?item-query=foobaritems`
But the `item-query is not a valid Python variable name`. The closed would be `item_query`. But you still need it to be exactly `item-query`, then you can declare a `alias`, and alias is what will be used to find the parameter value:
Ex:
```
from typing import Annotated

from fastapi import FastAPI, Query

app = FastAPI()


@app.get("/items/")
async def read_items(q: Annotated[str | None, Query(alias="item-query")] = None):
    results = {"items": [{"item_id": "Foo"}, {"item_id": "Bar"}]}
    if q:
        results.update({"q": q})
    return results
```

#### Custom Validation
There could be cases where you need to do some custom validation that cant be done with the parameters shon above. In those cases, you can use a custom validator function that is applied after the normal validation.
You can achieve that using Pydantics `AfterValidator` inside of `Annotated`.
Ex:
```
import random
from typing import Annotated

from fastapi import FastAPI
from pydantic import AfterValidator

app = FastAPI()

data = {
    "isbn-9781529046137": "The Hitchhiker's Guide to the Galaxy",
    "imdb-tt0371724": "The Hitchhiker's Guide to the Galaxy",
    "isbn-9781439512982": "Isaac Asimov: The Complete Stories, Vol. 2",
}


def check_valid_id(id: str):
    if not id.startswith(("isbn-", "imdb-")):
        raise ValueError('Invalid ID format, it must start with "isbn-" or "imdb-"')
    return id


@app.get("/items/")
async def read_items(
    id: Annotated[str | None, AfterValidator(check_valid_id)] = None,
):
    if id:
        item = data.get(id)
    else:
        id, item = random.choice(list(data.items()))
    return {"id": id, "name": item}
```