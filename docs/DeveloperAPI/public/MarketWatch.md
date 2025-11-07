#  Market Watch 

The **Market Watch API** allows you to fetch the list of instruments currently being tracked in the user's workspace. It returns instrument tokens that can be used for quotes, option chains, and order placements.

---

##  Endpoint

| Method | URL                             |
|--------|----------------------------------|
| GET    | `/api/marketWatch`   |

---

##  Authentication

| Auth Type     | Required | Description                          |
|---------------|----------|--------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

>  The token must be passed in the `Authorization` header in the format:  
> `Bearer <your_token>`

---

##  Request Details

###  Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes      | JWT token for the logged-in user. |

### Request Body 

_No request body or query parameters are required._

---

## Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    1010010000006232
  ]
}
```
#  Response Fields

| Field     | Type      | Description                                                         |
|-----------|-----------|---------------------------------------------------------------------|
| `status`  | `string`  | Response status (e.g., `"success"`, `"error"`).                    |
| `message` | `string`  | Descriptive message from the server.                               |
| `data`    | `array`   | List of instrument tokens in the user's **Market Watch**.          |

