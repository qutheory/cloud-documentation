# Admin API

Microservice for managing projects, billing, and authorization.

## Overview

The Admin API is responsible for enrolling new users, allowing users to manage their accounts, teams, and projects, and giving users authorization to other microservices.

![screen shot 2017-02-22 at 6 47 13 pm](https://cloud.githubusercontent.com/assets/1342803/23224609/5c33811a-f92f-11e6-8088-ab2876a3f864.png)

### Tokens

Two tokens are created when a user logs in:

- Access token
- Refresh token

#### Access Token

The access token is used to authenticate and authorize access to other microservices. It is a JWT that uses asymmetric signing. This allows the microservices (and all other parties) to verify the authenticity of the tokens using the public key. To learn more about this auth process, see [Keychain](https://github.com/vapor-cloud/keychain).

#### Refresh Token

The reresh token is used to get new access tokens after they expire. Refresh tokens are valid for long periods of time and can be used in place of user credentials to create access tokens. In other words, keep these safe. Refresh tokens should *never* be sent to microservices besides the Admin API or third parties.

### Authorization

Authorization for other microservices happens via the JWT access token and calls to the Admin API.

The access token contains identifying information about the user, as well as limited authorization information.

If the microservice requires more information about what specific permissions a user has, they can query the Admin API using the token.

## Usage

Instructions and examples for using the various RESTful endpoints.

### Create User

To create a user, supply an email, password, and name.

```http
POST api.vapor.cloud/admin/users
```

```json
{
  "email":"foo@vapor.codes",
  "password":"v@p0r_rUl3z",
  "name": {
    "first":"Foo",
    "last":"Bar"
  }
}
```

The API will respond with the created user.

```http
200 OK
```

```json
{
  "id": "0AFFA344-E804-461E-82A8-DE460CB43C75",
  "email": "foo@vapor.codes",
  "name": {
    "first": "Foo",
    "last": "Foo",
    "full": "Foo Bar"
  }
}
```


### Login

To login, supply the email and password of a previously created user.

```http
POST api.vapor.cloud/admin/login
```

```json
{
  "email":"foo@vapor.codes",
  "password":"v@p0r_rUl3z"
}
```

The API will respond with the access and refresh tokens.

```http
200 OK
```

```json
{
  "access_token": "<your_access_token>",
  "refresh_token": "<your_refresh_token>"
}
```

### Authed User

To test an access token, you can request the authenticated user.

```http
GET api.vapor.cloud/admin/me
Authorization: Bearer <your_access_token>
```

The API will respond with the same user information presented upon account creation.

```http
200 OK
```

```json
{
  "id": "0AFFA344-E804-461E-82A8-DE460CB43C75",
  "email": "foo@vapor.codes",
  "name": {
    "first": "Foo",
    "last": "Foo",
    "full": "Foo Bar"
  }
}
```

### Refresh

If your access token expires, you can get a new one using the refresh token.

```http
GET api.vapor.cloud/admin/refresh
Authorization: Bearer <your_refresh_token>
```

The API will respond with a new access token.

```http
200 OK
```

```json
{
  "access_token": "<your_new_access_token>"
}
```
