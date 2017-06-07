# NodeJS JWT Authentication

A simple server with JWT authentication. No real database connected, just in memory users!

## Starting

Simply run `npm install` to get all the dependencies and `npm start` to start the server!

## APIs

### User APIs

#### POST `/users`

You can do a POST to `/users` to create a new user.

The body must have:

* `username`: The username
* `password`: The password

It returns the following:

```json
{
  "id_token": {jwt}
}
```

The JWT is signed with the secret located at the `config.json` file. That JWT will contain the `username`.

#### POST `/users/login`

You can do a POST to `/users/login` to log a user in.

The body must have:

* `username`: The username
* `password`: The password

It returns the following:

```json
{
  "id_token": {jwt}
}
```

The JWT is signed with the secret located at the `config.json` file. That JWT will contain the `username`.

### Information API

#### GET `/api/information`

It returns a String with `title` and `msg`. It doesn't require authentication.

#### GET `/api/protected/information`

It returns a String with `title` and `msg`. It requires authentication.

The JWT must be sent on the `Authorization` header as follows: `Authorization: Bearer {jwt}`

## Credits

This server was inspired by the work of the Auth0 team and their [JWT example](https://github.com/auth0-blog/nodejs-jwt-authentication-sample)
