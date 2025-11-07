The **Toggle Favorite Strategy API** allows users to mark a specific strategy as a favorite or remove it from favorites.

---

## Endpoint

| Method | URL                                                            |
|--------|-----------------------------------------------------------------|
| GET    | `/api/strategies/marketPlace/{strategyName}/toggleFavorite`       |

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
| Authorization | Bearer `<token>`    | Yes      | JWT token for the authenticated user. |

### Body / Query Params

_No request body or query parameters are required._

---

### Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": "Successfully BankNifty Rider strategy favorite."
}
```
## Response Fields

| Field     | Type   | Description                                                                 |
|-----------|--------|-----------------------------------------------------------------------------|
| `status`  | string | The status of the response (e.g., `"success"`, `"error"`).                  |
| `message` | string | A descriptive message providing additional details about the request result. |
| `data`    | string | A message indicating the success or failure of the toggle favorite action.   |
