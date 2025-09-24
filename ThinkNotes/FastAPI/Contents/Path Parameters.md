#### What are path parameters?
- Path parameters can be used to make a endpoint dynamic it is same like passing arguments to a function.
- Here we mention parameters in the path itself and this parameters then are passed to "path operation function" as a argument.
```
from fastapi import FastAPI

app = FastAPI()


@app.get("/items/{item_id}")
async def read_item(item_id):
    return {"item_id": item_id}
    
```
- The value of the path parameter `item_id` will be passed to your function as the argument `item_id`
- Type of the path parameter can in the function can be defined by using standard python annotations.
- The path parameter name and the function argument name should be same.


#### Order matters!
- While creating path operations, there will be situations where you have a fixed path.
- Like *ex: /users/me*, it gives data of "current user."
- And then also you want to access data of a "specific user path" by some user_id *ex: users/{user_id}*
- This path orders are evaluated in order, it is necessary the "current user path" is declared before the "specific user path".
- This is done inorder to avoid error. As the "specific user" can match for the "current user", thinking that its receiving parameter "me" as "user_id" which will further give error as the "user_id" need *integer* and "me" is a *string*

#### Predefined Values
If you have a path operation that receives a path parameter, but you want the possible valid path parameter values to be predefined, you can use standard Python Enum.

This is done to define a predefined path means to already define the path and execute and return response associated with it.

#### Path parameters containing path
If inside the path parameter there is parameter which itself has a path as a value.
ex: path = `/files/{file_path}`
file path = `home/johndoe/myfile.txt`
hence full path becomes = `/files/home/johndoe/myfile.txt`
This is not supported by the OpenAPI to declare the path parametert to contain a path inside, as that could lead to scenarios that are difficult to test and define.

For this we use **Path Converter**
In the above case, the name of the parameter is `file_path`, and the last part, `:path`, tells that the parameter should match any path.
ex: `/files/{file_path:path}`
