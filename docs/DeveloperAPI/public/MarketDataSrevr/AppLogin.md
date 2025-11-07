The **app_login API** is used to authenticate a user and retrieve an `accessToken`. This token is required for making authenticated requests to other APIs.

---

## Endpoint

| Method | URL                    |
|--------|------------------------|
| POST   | `/api/app_login`        |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## Request Body

| Field    | Type   | Description                               | Required |
|----------|--------|-------------------------------------------|----------|
| appKey   | string | The application key provided to the user. | Yes      |
| userId   | string | The user’s unique identifier (email).     | Yes      |

### Example

```json
{
  "appKey": "<appkey>",
  "userId": "<userId>"
}
### Successful Response (200 OK)
```json 
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "accessToken": "<acesstoken>"
  }
}
```
### Error Response (400 / 500)
```json
{
  "status": "error",
  "message": "Invalid or missing username/password.",
  "error": "Both username and password fields are required."
}
```

