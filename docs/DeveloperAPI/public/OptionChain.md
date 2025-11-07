The **Option Chain API** allows clients to retrieve a list of instruments along with their associated instrument IDs. This endpoint is useful for obtaining available options data that can be used to subscribe to live market updates or further details about specific instruments.

---

### Endpoint

| Method | URL                    |
|--------|------------------------|
| GET    | `/api/optionChain`     |

---

### Parameters

#### Query Parameters

- **None required.**

---

### Request Headers

| Header        | Value                   | Required |
|---------------|-------------------------|----------|
| Authorization | `Bearer <your_token>`   | Yes      |
| Content-Type  | `application/json`      | Yes      |
| Accept        | `*/*`                   | Yes      |

---

### Successful Response (200 OK)
# Example
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
```
# Field Discription
| Field   | Type   | Description                                                                 |
|---------|--------|-----------------------------------------------------------------------------|
| status  | string | Status of the API response (e.g., `"success"` or `"error"`)                 |
| message | string | A short message confirming the result of the request                        |
| data    | object | An array of instrument objects |