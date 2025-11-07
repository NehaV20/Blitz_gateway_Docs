#  Favourite Instruments 

The **Favourite Instruments API** returns the list of instrument tokens marked as favourites by the user in their workspace. These tokens can be used for quick access, watchlists, and trade setups.

---

##  Endpoint

| Method | URL                             |
|--------|----------------------------------|
| GET    | `/api/favourite`     |

---

##  Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

>  Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

##  Request Details

###  Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes     | JWT token for the authenticated user. |

###  Body / Query Params

_No request body or query parameters are required._

---

##  Success Response

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    1010010002000001,
    1010010002000002
  ]
}
```
## Response Fields

| Field     | Type      | Description                                                         |
|-----------|-----------|---------------------------------------------------------------------|
| `status`  | `string`  | Response status (e.g., `"success"`, `"error"`).                    |
| `message` | `string`  | Descriptive message from the server.                               |
| `data`    | `array`   | List of instrument tokens marked as **favourites** by the user.    |
