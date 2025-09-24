Use `HTTPException` to raise an exception. As this is a exception you raise it and not return it. It is used to tell user that:
- Doesnt have access to that resource.
- Doesnt have enough priviliage for that operation
- The item is not available.

#### Raising a HTTPException in code:
```
from fastapi import FastAPI, HTTPException

app = FastAPI()

items = {"foo": "The Foo Wrestlers"}


@app.get("/items/{item_id}")
async def read_item(item_id: str):
    if item_id not in items:
        raise HTTPException(status_code=404, detail="Item not found")
    return {"item": items[item_id]}
```

Here the client will get an error that the "Item not found" when he will hit a query parameter other than foo. When raising an erro it not mandotary to only pass `str`, you can pass any like `dict`, or a `list`. FastAPI handles it and automatically convert it to JSON.