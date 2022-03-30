# Best-Nodejs-User-Authentication

An advance user authentication system with refresh and access jwt tokens

# Workflow
* When User does log in, send 2 tokens (Access token, Refresh token) in response to the client.
* Access token will have less expiry time and Refresh will have long expiry time.
* Client (Front-end) will store JWT token in his localStorage and Refresh token in Cookie Storage with HttpOnly and Secure flags.
* Client will use an Access token for calling APIs. But when it expires, pick the Refresh token from cookies and call Auth server API to get the new token.
* Auth server will have an API exposed which will accept Refresh token and checks for its validity and return a new Access token.
* Once the Refresh token is expired, the User will be logged out.

