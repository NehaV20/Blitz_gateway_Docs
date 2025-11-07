The **Create Clients API** allows the admin to create a new client in the system. On successful creation, it returns the new client’s unique ID, system-generated password, and username.

---

## Endpoint

| Method | URL                 |
|--------|----------------------|
| POST   | `/api/admin/client` |

---

## Headers

| Header        | Value                | Required |
|---------------|----------------------|----------|
| Content-Type  | `application/json`    | Yes      |
| Accept        | `application/json`    | Yes      |
| Authorization | `Bearer {accessToken}`| Yes      |

---

## Request Body

```json
{
  "userId": "string",
  "firstName": "string",
  "lastName": "string",
  "clientId": "string",
  "clientType": "Individual",
  "branchId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
  "phoneNumber": "string",
  "email": "user@example.com",
  "address": "stringstri",
  "city": "string",
  "pinCode": 0,
  "country": "string",
  "panNumber": "GWNOM6230P",
  "dateOfBirth": "26-06-2741",
  "exchangeSegments": [
    {
      "exchangeSegment": "NONE",
      "isEnabled": true,
      "participantCode": "string",
      "ctclId": "string",
      "accountId": "string",
      "adaptorId": "string",
      "clearingFirmId": "string",
      "keyInfo1": "string",
      "keyInfo2": "string"
    }
  ]
}
```
### Successful Response (200 OK)
```json
{
    "status": "success",
    "message": "Request processed successfully.",
    "data": {
        "id": "a1cf4151-cb6d-41c1-bb28-fe10b9bf7804",
        "userName": "USR789101",
        "password": "XgJ;,enk4?F{h4N",
        "exchangeSegments": null
    }
}