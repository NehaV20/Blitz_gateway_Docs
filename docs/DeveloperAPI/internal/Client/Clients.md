
The **Get All Clients API** allows an admin user to fetch a list of all registered clients along with their basic profile information. This endpoint is secured and requires a valid **Bearer Token**.

---

### Endpoint

| Method | URL                   |
|--------|-----------------------|
| GET    | `/api/admin/clients` |

---

### Request Headers

| Header         | Value                | Required |
|----------------|----------------------|----------|
| Content-Type   | application/json      | Yes      |
| Accept         | application/json      | Yes      |
| Authorization  | Bearer `<accessToken>`  | Yes      |

---

### Authorization

This endpoint requires an admin's Bearer Token in the `Authorization` header.

---

### Response Fields

| Field     | Type    | Description                           |
|-----------|---------|---------------------------------------|
| status    | string  | Status of the response (`"success"` or `"error"`) |
| message   | string  | A message confirming the result       |
| data      | array   | List of client objects                |

#### Each Client Object Contains:

| Field       | Type   | Description                        |
|-------------|--------|------------------------------------|
| id          | string | Unique client ID                   |
| userId      | string | Unique user ID                     |
| firstName   | string | Client's first name                |
| lastName    | string | Client's last name                 |
| phoneNumber | string | Client's phone number              |
| email       | string | Client's email address             |
| panNumber   | string | Client's PAN number                |
| address     | string | Client's address                   |
| city        | string | Client's city                      |
| pinCode     | number | Client's postal code (PIN code)    |

---

### Example Response

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
