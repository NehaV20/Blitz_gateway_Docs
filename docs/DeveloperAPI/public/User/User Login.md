

The **Login API** allows users to authenticate and obtain an **access token** and **refresh token** required for accessing other protected resources in the system. This API is used to securely log in users and retrieve necessary authentication tokens.

---

### Endpoint

| Method | URL                                |
|--------|------------------------------------|
| POST   | `/api/authentication/login`        |

---

### Parameters

#### Request Body

| Field    | Type   | Description                                                  |
|----------|--------|--------------------------------------------------------------|
| userName | string | The username for the login (e.g., `demouser`)                |
| password | string | The password for the user account (e.g., `Test@123`)         |

##### Example Request Body

```json
{
  "userName": "demouser",
  "password": "Test@123"
}
```
### Request Headers

| Header         | Value               | Required |
|----------------|---------------------|----------|
| Content-Type   | `application/json`   | Yes      |
| Accept         | `application/json`   | Yes      |

## Successful Response (200 OK)
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "accessToken": "<access_token>",
    "refreshToken": "<refresh_token>",
    "marketDataApiKey": "<market_data_api_key>"
  }
}
```
### Fields Description

| Field          | Type   | Description                                                                 |
|----------------|--------|-----------------------------------------------------------------------------|
| status         | string | Status of the API response (e.g., `"success"` or `"error"`)                 |
| message        | string | A short message confirming the result of the request                        |
| data           | object | Contains the authentication tokens (`accessToken`, `refreshToken`, `marketDataApiKey`) |
| accessToken    | string | The token required for accessing protected resources in the system         |
| refreshToken   | string | A token used to refresh the access token when it expires                    |
| marketDataApiKey | string | The API key used for market data access                                     |


