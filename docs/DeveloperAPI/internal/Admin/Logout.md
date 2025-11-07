# Logout API

## Overview

The **Logout API** invalidates the current access token, effectively logging the admin user out of the system. This endpoint helps in safely ending the user session and ensuring tokens can't be reused.

---

## Endpoint

| Method | URL                                       |
|--------|--------------------------------------------|
| POST   | `/api/authentication/logout`              |

---

## Headers

| Header         | Value                   | Required |
|----------------|-------------------------|----------|
| Authorization  | Bearer `<ACCESS_TOKEN>` | Yes      |
| Accept         | */*                     | Yes      |

---

## Request Body

No request body is required.

---

## ✅ Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Logout successful."
}
```
| Field   | Type   | Description                        |
|---------|--------|------------------------------------|
| status  | string | Response status (e.g., `"success"`) |
| message | string | Message confirming logout          |


```json
{
  "status": "error",
  "message": "Invalid or expired token.",
  "error": "unauthorized"
}
```
| Field   | Type   | Description                             |
|---------|--------|-----------------------------------------|
| status  | string | Error status (e.g., `"error"`)          |
| message | string | Message describing the error            |
| error   | string | Specific error message or code          |

