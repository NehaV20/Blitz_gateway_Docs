The **Favorite Strategies API** fetches a list of strategies that the user has marked as their favorites.

---

## Endpoint

| Method | URL                                         |
|--------|---------------------------------------------|
| GET    | `/api/strategies/marketPlace/favorites`     |

---

## Authentication

| Auth Type    | Required | Description                                      |
|--------------|----------|--------------------------------------------------|
| Bearer Token | Yes      | Use a valid JWT in the `Authorization` header.   |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### Headers

| Header        | Value              | Required | Description                          |
|---------------|--------------------|----------|--------------------------------------|
| Authorization | Bearer `<token>`   | Yes      | JWT token for the authenticated user |

### Body / Query Params

_No request body or query parameters are required._

---

### Successful Response (200 OK)
Example:
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    "BankNifty Rider"
  ]
}
```
### Response Fields

| Field      | Type   | Description                                                             |
|------------|--------|-------------------------------------------------------------------------|
| `status`   | string | The status of the response (`"success"` or `"error"`).                 |
| `message`  | string | A message providing additional information about the request.          |
| `data`     | array  | A list containing the names of the user's favorite strategies.          |
| `data[]`   | string | The name of a favorite strategy (e.g., `"BankNifty Rider"`).            |
