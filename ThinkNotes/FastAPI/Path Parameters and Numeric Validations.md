In the same way that you can declare more validations and metadata for query parameters with `Query`, you can declare the same type of validations for the path parameters with `Path`

#### Number validations: greater than or equal
With the help of Query and Path you can declare number constraints. Here, with `ge = 1`, item_id will need to be an integer greater than equal to 1.

```
from typing import Annotated

from fastapi import FastAPI, Path

app = FastAPI()


@app.get("/items/{item_id}")
async def read_items(
    item_id: Annotated[int, Path(title="The ID of the item to get", ge=1)], q: str
):
    results = {"item_id": item_id}
    if q:
        results.update({"q": q})
    return results
```

#### Number validations: greater than and less than or equal
- `gt`: greater than
- `le`: less than
- `ge`: greater than or equal
- `lt`: less than
- `le`: less than or equal

**Note**: Query, Path and other classes are subclasses of a common Param class. All of them share the same parameters for additional validation and metadata you have seen.


