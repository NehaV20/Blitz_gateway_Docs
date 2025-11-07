The **Strategy Instances API** retrieves the instances of a specific strategy, identified by the `strategyId`. It provides details about the instances, including their status, creation time, and last updated time.

---

## Endpoint

| Method | URL                                                     |
|--------|---------------------------------------------------------|
| GET    | `/api/strategies/{strategyId}/instances`                 |

---

## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### URL Parameters

| Parameter    | Description                                        |
|--------------|----------------------------------------------------|
| `strategyId` | The unique identifier of the strategy whose instances are being retrieved. |

### Headers

| Header        | Value                  | Required | Description                       |
|---------------|------------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`        | Yes      | JWT token for the authenticated user. |

### Body / Query Params

_No request body or query parameters are required._

---

### Successful Response (200 OK)
Example:
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
