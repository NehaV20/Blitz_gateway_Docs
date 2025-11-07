The **Get Trade Orders API** fetches the list of trades executed under the authenticated user's workspace. It returns all trade-level order details linked with strategy executions.

---

## Endpoint

| Method | URL                      |
|--------|--------------------------|
| GET    | `/api/order/trades`     |

---

## Authentication

| Auth Type     | Required | Description                                      |
|---------------|----------|--------------------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header.     |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### Headers

| Header        | Value               | Required | Description                            |
|---------------|---------------------|----------|----------------------------------------|
| Authorization | Bearer `<token>`    | Yes      | JWT token for the authenticated user.  |

### Body / Query Params

_No request body or query parameters are required._

---

## Success Response

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
```
## Response Fields

| Field     | Type    | Description                                                              |
|-----------|---------|--------------------------------------------------------------------------|
| `status`  | string  | Response status (e.g., `"success"`, `"error"`).                          |
| `message` | string  | Descriptive message from the server.                                     |
| `data`    | array   | List of trade-level order objects associated with the user.              |

> **Note:** `data` is currently shown as an empty array (`[]`) in the sample response. Actual responses will include trade objects when trades exist.
