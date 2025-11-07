# Access Token 

## Overview

After successful login via the Admin Login API, an `accessToken` is returned. This token is a **JWT (JSON Web Token)** used to authenticate subsequent requests to all **protected admin endpoints**.

---

## Access Token Format

The token is a long, encoded string. 

 ```json
{
    "accessToken": "<JWT_ACCESS_TOKEN>",
}
```
### Headers

| Header           | Value                           |
|------------------|----------------------------------|
| Authorization    | Bearer `<accessToken>`          |
| Content-Type     | application/json                |
| Accept           | */*                             |

## Token Expiry

- Access tokens are **time-bound** and will expire after a predefined duration (defined on the server).
- On expiry, the server will respond with an **unauthorized (401)** error.
- Use the `refreshToken` to generate a new `accessToken` without re-login.

## Response Field 

| Field           | Type     | Description                              |
|------------------|----------|------------------------------------------|
| accessToken      | string   | JWT token used in headers for authentication |
| refreshToken     | string   | Used to obtain a new access token         |
| marketDataApiKey | string/null | Reserved field, currently unused        |

