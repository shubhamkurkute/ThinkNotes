For declaring the group of query parameters which are interrelated we can use Pydantic to declare them.
This would allow you to re-use the model in multiple places and also to declare validations and metadata for all the parameters at once.

#### Query Parameters with a Pydatic Model
Declare the query parameters that you need in a Pydantic model and then declare the parameter as `Query`

```
from typing import Annotated, Literal

from fastapi import FastAPI, Query
from pydantic import BaseModel, Field

app = FastAPI()


class FilterParams(BaseModel):
    limit: int = Field(100, gt=0, le=100)
    offset: int = Field(0, ge=0)
    order_by: Literal["created_at", "updated_at"] = "created_at"
    tags: list[str] = []


@app.get("/items/")
async def read_items(filter_query: Annotated[FilterParams, Query()]):
    return filter_query
```

FastAPI will extracct the data for each field from the query parameters int the request and give you the Pydantic model you defined.

#### Forbid Extra Query Parameters
Some of the cases you need to restrict the query parameters you want to receive. Pydantic provides the model configuration to forbid any extra fields.

```
from typing import Annotated, Literal

from fastapi import FastAPI, Query
from pydantic import BaseModel, Field

app = FastAPI()


class FilterParams(BaseModel):
    model_config = {"extra": "forbid"}

    limit: int = Field(100, gt=0, le=100)
    offset: int = Field(0, ge=0)
    order_by: Literal["created_at", "updated_at"] = "created_at"
    tags: list[str] = []


@app.get("/items/")
async def read_items(filter_query: Annotated[FilterParams, Query()]):
    return filter_query
```

If the client tries send to send the extra query parameters then it will give an error.