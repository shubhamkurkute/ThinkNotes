Dependency injection means in programming that there is a way for your code to declare things that it requires to work and use. And then, that system will take care if doing whatever is needed to provide your code with those needed dependencies.

```
from typing import Annotated

from fastapi import Depends, FastAPI

app = FastAPI()


async def common_parameters(q: str | None = None, skip: int = 0, limit: int = 100):
    return {"q": q, "skip": skip, "limit": limit}


CommonsDep = Annotated[dict, Depends(common_parameters)]


@app.get("/items/")
async def read_items(commons: CommonsDep):
    return commons


@app.get("/users/")
async def read_users(commons: CommonsDep):
    return commons
```

- So the depends function work like it takes all the parameter that are in path opration function and checks it.
- Whenever request arrives at FastAPI:
	- Calls the dependency function with the correct parameters.
	- Gets the result from your fucntion
	- Assign that result to the parameter in your path operation function

- The key factor is that dependency should be "callable".
- A "callable" in Python is anything that Python can "call" like a function.
- Dependency can be used in the path as well if you dont require any return values.
- Also not just function but a class can be created for dependency injection.
- One path operation function can depend on multiple dependencies.


### Dependency with yield
Instead of return we use yield and write extra code after that.

#### A database dependency with yield.
You could use this to create a database session and close it after finishing.

```
async def get_db():
    db = DBSession()
    try:
        yield db
    finally:
        db.close()
```
