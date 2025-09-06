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
