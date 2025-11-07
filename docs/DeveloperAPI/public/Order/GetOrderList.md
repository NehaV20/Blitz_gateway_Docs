The Get Orders API retrieves all the orders placed by the user along with related metadata such as strategy instance details, execution type, and completion status. This is helpful for displaying order books, strategy states, and execution records.

## Endpoint

| Method | URL         |
|--------|-------------|
| GET    | `/api/order` |

---

##  Authentication

| Auth Type     | Required | Description                                      |
|---------------|----------|--------------------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the `Authorization` header.  |

> Example:
>
> `Authorization: Bearer <your_token>`

---

###  Headers

| Header        | Value            | Required | Description                           |
|---------------|------------------|----------|---------------------------------------|
| Authorization | Bearer `<token>` | Yes      | JWT token for the authenticated user. |

###  Query Params

_No request body or query parameters are required._

---

### Successful Response (200 OK)
# Example

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    {
      "entityId": "dfe1afd5-b871-4ea3-9388-1ec130de7e5f",
      "strategyId": "36250ee3-ad08-4e09-862f-83deee8cdef9",
      "strategyInstanceId": "975e5ebe-4a72-4a66-853e-602ea297089c",
      "strategyInstanceName": "HDFCBANK",
      "strategyName": "ManualTrading",
      "executionType": 1,
      "isOrderCompleted": false,
      "userText": "",
      "rmsTag": "A",
      "panId": "PABSU0987S",
      "clearingFirmId": "6546516",
      "algoCategoryId": "FGS961",
      "algoId": "ASFXC123S56"
    }
  ]
}
```
## Response Fields

| Field     | Type      | Description                                                                 |
|-----------|-----------|-----------------------------------------------------------------------------|
| `status`  | `string`  | Response status (e.g., `"success"`, `"error"`).                            |
| `message` | `string`  | Descriptive message from the server.                                       |
| `data`    | `array`   | List of order objects with strategy, execution, and user details.          |

### `data` Fields (Order Object)

| Field                  | Type      | Description                                                  |
|------------------------|-----------|--------------------------------------------------------------|
| `entityId`             | `string`  | Unique identifier of the order entity.                      |
| `strategyId`           | `string`  | ID of the strategy the order belongs to.                    |
| `strategyInstanceId`   | `string`  | ID of the running strategy instance.                        |
| `strategyInstanceName` | `string`  | Friendly name of the instance (e.g., `"RELIANCE"`).         |
| `strategyName`         | `string`  | Name of the strategy (e.g., `"ManualTrading"`).             |
| `executionType`        | `number`  | Order execution type (e.g., 1 = Manual, 2 = Algo).          |
| `isOrderCompleted`     | `boolean` | Whether the order is completed or still active.             |
| `userText`             | `string`  | Optional notes added by the user.                           |
| `rmsTag`               | `string`  | Risk Management tag used for classification.                |
| `panId`                | `string`  | PAN number of the user associated with the order.           |
| `clearingFirmId`       | `string`  | Identifier of the clearing firm.                            |
| `algoCategoryId`       | `string`  | ID for the algo category.                                   |
| `algoId`               | `string`  | ID for the specific algo logic used.                        |
