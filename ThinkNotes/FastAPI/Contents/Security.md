**OAuth2**
- OAuth2 is a specification that defines several ways to handle authentication and authorization.
- It includes ways to understand using "third party"

#### The `password` flow
- The password flow is one of the ways defined in OAuth2, to handle security and authentication.
- OAuth2 was designed so that the backened is independent of the server which handles the authentication. of the user.
- When user enters a username and password in the frontend, then the frontend sends the password and username to a specific url in our API. This API checks the username and the password and responds with a token. This token is stored somewhere in the frontend and has expiry so that user has to enter the details again after the expiration.
- When user wants to access another webpage of our web app then frontend needs to fetch more data from the API.
	- But to do it needs authentication for that specific endpoint
	- So, it can authenticate with our API, it sends a header with Authentication with a value of bearer along with the token.

#### Get username and password
OAuth2 specifies that when using the "password flow" the client/user must send a username and password fields as a form data. This username and password must be send as a form data.
- spec also says that the client can send another form field 'scope'.
- They are normally used to declare specific security permissions, for example:
	- users:read or users:write are common examples

## About JWT
- JWT means "JSON web token". Its a long string without spaces. It is not encrypted i.e. it can be used to recover the information from the contents.
- But its signed. We can verify that who actually emitted this token.
- That way this helps in to create a token with expiry.