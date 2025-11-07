The **Refresh Token API** allows users to obtain a new access token using a valid refresh token. This is useful when the original access token has expired, and you want to continue accessing protected resources without logging in again.

---

### Endpoint

| Method | URL                                   |
|--------|----------------------------------------|
| POST   | `/api/authentication/refreshToken`     |

---

### Request Headers

| Header        | Value               | Required |
|---------------|---------------------|----------|
| Content-Type  | application/json     | Yes      |
| Accept        | application/json     | Yes      |

---

### Request Body

| Field        | Type   | Description                     |
|--------------|--------|---------------------------------|
| refreshToken | string | The refresh token received during login |

#### Example Request Body

```json
{
  "refreshToken": "your_refresh_token_here"
}
```
### Field Discription

| Field            | Type   | Description                                                                |
|------------------|--------|----------------------------------------------------------------------------|
| status           | string | Status of the API response (e.g., `"success"` or `"error"`)                |
| message          | string | A short message confirming the result of the request                       |
| data             | object | Contains the new tokens (`accessToken`, `refreshToken`, `marketDataApiKey`)|
| accessToken      | string | The new access token to access protected resources                         |
| refreshToken     | string | A new refresh token                                                        |
| marketDataApiKey | string | The API key used for accessing market data (can be `null`)                 |

