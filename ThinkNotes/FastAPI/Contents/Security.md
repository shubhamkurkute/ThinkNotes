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
	- 