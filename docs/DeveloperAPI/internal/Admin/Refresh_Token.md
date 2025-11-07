# Refresh Token API

## Overview

The **Refresh Token API** is used to generate a new `accessToken` when the current one has expired. This allows admins to stay authenticated without having to re-login.

---

## Endpoint

| Method | URL                                   |
|--------|----------------------------------------|
| POST   | `/api/authentication/admin/refresh`   |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## Request Body

```json
{
  "refreshToken": "<JWT_REFRESH_TOKEN>"
}
```
| Field        | Type   | Required | Description                                |
|--------------|--------|----------|--------------------------------------------|
| refreshToken | string | Yes      | The refresh token received during login    |


## Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Token refreshed successfully.",
  "data": {
    "accessToken": "<NEW_ACCESS_TOKEN>",
    "refreshToken": "<NEW_REFRESH_TOKEN>"
  }
}

```
| Field             | Type   | Description                                      |
|-------------------|--------|--------------------------------------------------|
| status            | string | Response status, e.g., `"success"`              |
| message           | string | Message describing the outcome                  |
| data.accessToken  | string | New access token used for API authentication    |
| data.refreshToken | string | New refresh token to continue session securely  |

## Error Response (401 Unauthorized)

```json
{
  "status": "error",
  "message": "Invalid or expired refresh token.",
  "error": "unauthorized"
}

```
| Field   | Type   | Description                             |
|---------|--------|-----------------------------------------|
| status  | string | Error status, e.g., `"error"`           |
| message | string | Message describing the error            |
| error   | string | Specific error code or message          |
