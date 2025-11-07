#  Time and Sales

The **Time and Sales API** provides a list of instrument tokens currently tracked under the user's time and sales workspace. These tokens are used for fetching trade tick data, LTP movements, and volume breakdowns.

---

##  Endpoint

| Method | URL                              |
|--------|-----------------------------------|
| GET    | `/api/timeAndSales`   |

---

##  Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

>  The token must be passed in the `Authorization` header in the format:  
> `Bearer <your_token>`

---

##  Request Details

###  Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes       | JWT token for the logged-in user. |


###  Request Body 

_No request body or query parameters are required._

---

## Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    1010010002000024,
    1010010002000025
  ]
}
```
## Response Fields

| Field     | Type      | Description                                                         |
|-----------|-----------|---------------------------------------------------------------------|
| `status`  | `string`  | Response status (e.g., `"success"`, `"error"`).                    |
| `message` | `string`  | Descriptive message from the server.                               |
| `data`    | `array`   | List of instrument tokens in the **Time & Sales** tracking list.   |

