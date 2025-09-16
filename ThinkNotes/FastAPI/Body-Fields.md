The same way you declare additional validation and metadata in path operation funtion parameters with Query, Path and Body, you can declare validation and metadata inside of Pydantic models using Pydantic's Field.

```
from typing import Annotated

from fastapi import Body, FastAPI
from pydantic import BaseModel, Field

app = FastAPI()


class Item(BaseModel):
    name: str
    description: str | None = Field(
        default=None, title="The description of the item", max_length=300
    )
    price: float = Field(gt=0, description="The price must be greater than zero")
    tax: float | None = None

```

Field works the same way as Query, Path and Body, it has all the same parameters, etc.

Actually Query, Path and others create a objects of subclasses of a common Param class, which is itself subclass of Pydantics FieldInfo class.And Pydantics Field returns an instance of FieldInfo as well.