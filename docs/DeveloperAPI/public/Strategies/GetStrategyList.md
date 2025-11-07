The **Strategy List API** retrieves a list of strategies available in the system, including details like their command parameters and values.

---

## Endpoint

| Method | URL                                        |
|--------|--------------------------------------------|
| GET    | `/api/strategies/list`                    |

---

## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---

## Request Details

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
  "data": [
    {
      "name": "Position",
      "dataType": "Int",
      "value": "0",
      "commands": [
        {
          "id": "03199b26-b5c9-4130-b384-81e9630c3823",
          "name": "PlaceOrder",
          "commandInputParameters": [
            {
              "name": "ComplexityType",
              "dataType": "Int",
              "value": "0"
            }
          ]
        }
      ]
    }
  ]
}
```
# Response Fields

| Field                          | Type   | Description                                                                 |
|--------------------------------|--------|-----------------------------------------------------------------------------|
| `status`                       | string | The status of the response (e.g., `"success"`, `"error"`).                  |
| `message`                      | string | A message providing additional information about the request.               |
| `data`                         | array  | An array containing the strategy data.                                      |
