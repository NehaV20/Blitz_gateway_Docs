The **Open Orders API** returns the list of orders that are currently open in the user's workspace. These orders represent the pending or unexecuted orders in the system.

---

## Endpoint

| Method | URL                             |
|--------|----------------------------------|
| GET    | `/api/order/openOrders`          |

---

## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes     | JWT token for the authenticated user. |

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

| Field     | Type     | Description                                                               |
|-----------|----------|---------------------------------------------------------------------------|
| `status`  | string   | Response status (e.g., `"success"`, `"error"`).                           |
| `message` | string   | Descriptive message from the server.                                      |
| `data`    | array    | List of open orders associated with the user.                              |
