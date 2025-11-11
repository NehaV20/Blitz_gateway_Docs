The **Change Password API** allows an authenticated user to securely change their password by providing the current password and the new password.

---

### Endpoint

| Method | URL                                      |
|--------|------------------------------------------|
| POST   | `/api/authentication/changePassword`     |

---

### Request Headers

| Header         | Value                | Required |
|----------------|----------------------|----------|
| Content-Type   | application/json      | Yes      |
| Accept         | application/json      | Yes      |
| Authorization  | `Bearer "<JWT_ACCESS_TOKEN>"`  | Yes      |

---

### Request Body

| Field              | Type   | Description                                       |
|--------------------|--------|---------------------------------------------------|
| userName           | string | The username of the user                          |
| currentPassword    | string | The user's current password                       |
| newPassword        | string | The new password to be set                        |
| confirmNewPassword | string | Confirmation of the new password                  |

#### Example Request Body

```json
{
  "confirmNewPassword": "<string>",
  "currentPassword": "<string>",
  "newPassword": "<string>",
  "userName": "<string>"
}
```

## Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "message": "Password changed successfully"
  }
}

```
