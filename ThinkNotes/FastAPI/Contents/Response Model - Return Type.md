You can declare the response or the return type by using path operation return type. Also can use annotations the same way you would for input data in function parameters, you can use Pydantic models, list, dictionaries, scaler values like integers, booleans etc.

FastAPI will use this return type to:
- **Validate the returned data**
	- If the data is invalid, it means that the app code is broken, and it will return the server error rather then returning the incorrect response or data.
- **Add a JSON schema for the response, in the OpenAPI path operation**
	- This will be used by the automatic docs
	- It will be used by the automatic client code genration tools
- It will also limit and filter the data in the response avoiding extra data to be send.

#### `response_model` Parameter
There are some cases where you need or want to return some data that is not exactly what the type declares. For example, you could want to return a dictionary or a database object, but declare it as a Pydantic model. This way the Pydantic model would do all the documentation, validation,etc for the object you have returned.
So its about creating a response model using a pydantic model.
```
from typing import Any

from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tax: float | None = None
    tags: list[str] = []


@app.post("/items/", response_model=Item)
async def create_item(item: Item) -> Any:
    return item


@app.get("/items/", response_model=list[Item])
async def read_items() -> Any:
    return [
        {"name": "Portal Gun", "price": 42.0},
        {"name": "Plumbus", "price": 32.0},
    ]
```

#### `response_model` Priority
If you declare both a return type and a response_model, the response_model will take priority and be used by FastAPI. This way you can add correct type annotations to your functions even when you are returning a type different than the response model.

#### Response Model Encoding Parameters
If the response model could have default values and you dont want to include those default values in the response, and only the values actually set. For example there are many attributes in the NoSQL database, but you dont want to send very long JSON responses full of default values.

Use the `response_model_exclude_unset` parameter and those default values wont be included in the response.

```
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tax: float = 10.5
    tags: list[str] = []


items = {
    "foo": {"name": "Foo", "price": 50.2},
    "bar": {"name": "Bar", "description": "The bartenders", "price": 62, "tax": 20.2},
    "baz": {"name": "Baz", "description": None, "price": 50.2, "tax": 10.5, "tags": []},
}


@app.get("/items/{item_id}", response_model=Item, response_model_exclude_unset=True)
async def read_item(item_id: str):
    return items[item_id]
```

Use the path operation decorators parameter `response_model` to define response models and especially to ensure private data is filtered out.
Use multiple Pydantic models and inherit freely for each case. You dont need to have a single data model per entity if that entity must be able to have different "states". As the case with the user "entity" with a state including password, password_has and no password.