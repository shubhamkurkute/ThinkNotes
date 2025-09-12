When you need to send a data from a client to your API, you send it as a request body. A request body is data sent by the client to your API. A response body is the data your API sends to the client.

For the declaration of the request body, you use Pydantic models with all their power and benefits.

What happens while validating:
- During the validation if the data is invalid, it will return a nice and clear error, indicating exactly where and what was the incorrect data.

#### Request Body + path parameters

So the fastAPI recognizes that the function parameters that match path parameters should be taken from the path, and that function parameters that are declared to be Pydantic models should be taken from the request body.

#### Request body + path + query parameters
Declare body, path and query parameters, all at the same time. FastAPI will recognize each of them and take the data from the correct place.
```
@app.put("/items/{item_id})
async def update_item(item_id:int, item:Item, q:str | None = None):
	result = {"item_id": item_id, **item.dict()}
	if q: 
		result.update({"q": q}) 
	return result
```

**The function parameters will be recognized as follows:**
- If the parameter is also declared in the path, it will be used as a path parameter
- If the parameter is of singular type it will be interpreted as a query parameter
- If the parameter is declared to be of the type of a Pydantic model, it will be interpreted as a request body.