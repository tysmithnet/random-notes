# Oauth2
An **authorization** framework not an *authentication* framework
## Id
20220221125949
## Tags
#oauth2 #authorization #authentication #auth #security
## Roles
### User
- person who is granting access to so some subset of their resource data/services
    - documents, photos, ability to post, transfer funds, login, etc
- any system that wants to act *as* or *on behalf of* someone needs the user's explicit permission
    - anytime you've allowed site X to `photos:modify`, `account:update`, `repo:delete`, etc on site Y
### Resource Server
- thing providing value
- also called the API
- *has* the things that are important to the user and the user will give permission to use
- must accept and validate tokens and grant the request if the token is valid
- doesn't need to know about the applications using the resources
### Authorization Server
- user interacts with the auth server when an application is requesting access to their resources
- server that displays the OAuth prompt
    - user will approve/deny the access
- server that grants access tokens to the application
### Client
- thing attempting to act on the user's behalf or use the user's resources
- needs to get and use a token
#### Confidential Clients
- can keep the client secret safe
- applications that run on private servers
- typically custom/private applications
- webapps are most common since the token lives with the maintainers of the web app
#### Public Clients
- can't keep client secret safe
- typically mobile and javascript based apps (SPA)
    - SPAs usually always have a server side endpoint that performs server-side oauth
    - access token can **NEVER** be given to the users browser
## Tokens
- Several types of tokens are communication between the various roles
### Access Token
- `string` used when making authenticated requests to the resource server
- has no meaning to the application using it
- represents that a user has authorized a third party app to access their account
- has an expiration date
- can contain information useful to the server
    - user id
    - list of scopes
### Refresh Token
- `string` used when getting a new token after the current one expires
- not all authorization servers provide this feature
### Authorization Code
- intermediate and temporary token used in server side app flow
- returned to the client from the authorization server after the user approves access
    - client then exchanges this for an access token
## Server-Side Apps
- most common type of app using oauth
- almost always confidential clients
- use the `authorization_code` grant type
- client and auth server have a channel between them
- user's browser interacts with the client
- client issues API requests to the resource server
    - user's browser never hitting API server directly
- after the user authorizes the client receives an *authorization code* which it can exchange for an access token