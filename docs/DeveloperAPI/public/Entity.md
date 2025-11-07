The **Entity API** fetches user-specific profile details including identification and enabled exchange segments.

---

## Endpoint

| Method | URL           |
|--------|---------------|
| GET    | `/api/entity` |

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
Examle:
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "id": "dfe1afd5-b871-4ea3-9388-1ec130de7e5f",
    "userId": "DEMOUSER",
    "firstName": "DEMO",
    "lastName": "USER",
    "phoneNumber": "9685741023",
    "email": "demouser@quantxpress.com",
    "exchangeSegments": [
      {
        "exchangeSegment": "NSEFO",
        "isEnabled": true,
        "participantCode": "",
        "ctclId": "",
        "accountId": "",
        "adaptorId": "",
        "clearingFirmId": "",
        "keyInfo1": "",
        "keyInfo2": ""
      }
    ]
  }
}
```
# Response Fields

| Field                          | Type   | Description                                                                 |
|--------------------------------|--------|-----------------------------------------------------------------------------|
| `status`                       | string | The status of the response (e.g., `"success"`, `"error"`).                  |
| `message`                      | string | A message providing additional information about the request.               |
| `data`                         | array  | An array containing the Entity data.                                      |
