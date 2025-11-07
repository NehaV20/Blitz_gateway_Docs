The **Subscribe to Instrument API** allows users to subscribe to a specific instrument for receiving live market updates. This API enables clients to subscribe to instruments without needing to manually update data.

---

### Endpoint

| Method | URL                                               |
|--------|----------------------------------------------------|
| POST   | `/api/user/instruments/subscribe`                  |

---

###  Parameters

#### Query Parameters

- **None required.**

---

###  Request Headers

| Header        | Value                  | Required |
|---------------|------------------------|----------|
| Authorization | `Bearer <your_token>`   | Yes      |
| Content-Type  | `application/json`      | Yes      |

---

### Request Body

```json
{
  "instrumentToken": "Bearer <your_token>"
}

# Successful Response (200 OK)
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "message": "User subscribed to instrument successfully."
  }
}
```
# Field Discription
| Field   | Type   | Description                                                                 |
|---------|--------|-----------------------------------------------------------------------------|
| status  | string | Status of the API response (e.g., `"success"` or `"error"`)                 |
| message | string | A short message confirming the result of the request                        |
| data    | object | Contains the confirmation message (`"User subscribed to instrument successfully."`) |