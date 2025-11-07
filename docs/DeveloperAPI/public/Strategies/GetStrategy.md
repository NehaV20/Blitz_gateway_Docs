The Strategy Statistics API returns a list of strategy-level statistics associated with a specific client. These statistics include performance metrics such as total trades, win rate, drawdown, Sharpe ratio, and more — useful for client dashboards or analytical reports.

## Endpoint

| Method | URL                             |
|--------|----------------------------------|
| GET    | `/api/strategies/statistics/{clientId}`         |

---
## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

---
### Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes     | JWT token for the authenticated user. |
| clientId      | string              | Unique Client ID (e.g., CLI654321)           |


---

### Body / Query Params

_No request body or query parameters are required._

---

### Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
```