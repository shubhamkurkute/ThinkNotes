sWhen you declare other function parameters that are not the part of the path parameters, they are automatically interpreted as "query" parameters. This means the parameter of the path operation function are not in operation path then the parameters of the function are called as query parameters.

The query is set of key value pairs that go after the `?` in a URL, separated by `&` characters.
For Example in URL:
`http://127.0.0.1:8000/items/?skip=0&limit=10`
In this th query parameters are
- `skip` with value of "0"
- `limit` with value of "10"
- This are naturally of string type. Type of this can be changed by defining the type in the function arguments.