This can be also define as same as Query, Path and Cookie parameters.

#### Automatic Conversion
Header has a little extra functionality on top of what Path, Query and Cookie provide. Most of the standard headers are separated bt hyphen character. But a variable like user-agent is invalid in Python. 
So by default Header will convert the parameter names characters from underscore to hyphen to extract and document the headers.
Also, HTTP headers are case-insensitive, so, you can declare them with standard Python style (also known as "snake_case").

#### Duplicate headers
It is possible to receive duplicate headers. That means same header with multiple values. So this can be converted to list of all values. By using type declaration of list.

## Header Parameter Models
Same as the Cookie that we can create a Pydantic model for group of related headers to use it any where, and also can forbid the extra data with the help of :
`model_config = {"extra":"forbid"}`
This is declared in Pydantic model.

#### Disable Convert Underscores
The same way as the regular header parameters, when you have underscore characters in the parameter names, they are automatically converted to hyphens.
We can also disable the automatic conversion, you can do it as well for pydantic models for header parameters.
Ex:
`headers: Annotated[CommonHeaders, Header(convert_underscores=False)],`

**Note: Before setting it to False bear in mind that some HTTP proxies and servers disallows the usage of headers with underscores.**