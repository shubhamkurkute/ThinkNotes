You can define cookie parameters same way you define `Query` and `Path` parameters.

The cookie parameters can be declared same as the Path and Query. You can define the defaut value as well as all the extra validation or annotation parameters.

## Cookie parameter Models
If you have of group of interrelated cookies, you can create a Pydantic model to declare them. This would allow you to reuse the model in multiple places and also to declare validations and metadata for all parameter at once.

#### Cookies with a Pydantic Model
Declare a cookie parameters that you need in a Pydantic Model, and then declare the parameter as Cookie.

#### Forbid extra cookies
So you can forbid extra cookies that you want to receive. If a client tries to send some extra cookies, they will receive an error response.