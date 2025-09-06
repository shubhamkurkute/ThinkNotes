
### Features
- A super fast python web framwework, and has asynchronous programming
- **Swagger Ui**: This is the UI to test the routes and test the endpoints
- **Pydantic**: This is provided by the fastapi which helps for data validation. Which is also used for type hinting.
- **Based on open standards**: Based on Open API standards. 
- **Security and Authentication:** 
	- Http Basic
	- Oauth2 (JWT : Json Web Token)
	- API keys in
		- Headers 
		- Query Parameters
		- Cookies etc.
- **Starlette Feature**: FastAPI is build on starlette framework which supports
	- Websocket support
	- GraphQL support
	- In-process background tasks
	- Startup and Shutdown events
	- Test Client builts on requests
	- CORS, GZip, Static Files, Streaming responses
	- Session and Cookie Support
- **Other Features**:
	- SQL Database
	- NoSQL Database
	- GraphQL

**Note**: Dynamic routhing should be below the static route having same base endpoint.

- **Path**: A path is commonly called as an endpoint or a route.
- **Operation**: Operation here refers to one of the HTTP "methods".
	- `POST`: to create data
	- `GET`: to read data
	- `PUT`: to update dat
	- `DELETE`: to delete data
	- In the HTTP protocol, you can communicate to each path using one of these "methods"
	- In OpenAPI, each of the HTTP methods is called an "operation".

- Starting code:
	- Import `FastAPI`
	- Create a `app` instance
	- Write a **path operation decorator** like `@app.get("/")`
	- Write a **path operation function** like `async def root()`
	- Run the developement with the `uvicorn main:app --reload`