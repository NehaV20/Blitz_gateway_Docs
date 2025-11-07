The **Get Client by User ID API** allows you to fetch the details of a specific client using their unique user ID.

---

## Endpoint

| Method | URL                                  |
|--------|--------------------------------------|
| GET    | `/api/admin/client/{userId}`         |

---

## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### URL Params

| Parameter   | Type   | Description                                  |
|-------------|--------|----------------------------------------------|
| `userId`    | string | The User ID for the client you want to fetch. |

### Headers

| Header        | Value               | Required | Description                       |
|---------------|---------------------|----------|-----------------------------------|
| Authorization | Bearer `<token>`    | Yes      | JWT token for the authenticated user. |

---

## Request Body
_No request body or query parameters are required._

### Successful Response (200 OK)
# Example
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "userId": "USR789101",
    "firstName": "Rahul",
    "lastName": "Mehta",
    "phoneNumber": "+91-9988776655",
    "email": "rahul.mehta@example.com",
    "address": "12 Marine Drive",
    "city": "Chennai",
    "pinCode": 600001,
    "country": "India",
    "exchangeSegments": [
      {
        "exchangeSegment": "BSECM",
        "isEnabled": true,
        "participantCode": "PCODEBSECM",
        "ctclId": "CTCL0789",
        "accountId": "ACC321",
        "adaptorId": "ADAPT001",
        "clearingFirmId": "CLEAR001",
        "keyInfo1": "KEY1BSE",
        "keyInfo2": "KEY2BSE"
      },
      {
        "exchangeSegment": "BSEFO",
        "isEnabled": true,
        "participantCode": "PCODEBSEFO",
        "ctclId": "CTCLB1",
        "accountId": "ACCB001",
        "adaptorId": "ADAPT002",
        "clearingFirmId": "CLEAR002",
        "keyInfo1": "KEY1FO",
        "keyInfo2": "KEY2FO"
      }
    ]
  }
}
