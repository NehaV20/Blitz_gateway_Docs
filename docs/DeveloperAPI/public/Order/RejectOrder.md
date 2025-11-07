# Rejected Orders

The **Rejected Orders API** retrieves a list of all rejected order attempts placed by the user in the workspace. These rejections may occur due to RMS, invalid parameters, or exchange issues.

---

## Endpoint

| Method | URL                               |
|--------|------------------------------------|
| GET    | `/api/order/rejectedOrders`       |

---

## Authentication

| Auth Type     | Required | Description                            |
|---------------|----------|----------------------------------------|
| Bearer Token  | Yes      | Use a valid JWT in the Authorization header. |

> Example:  
> `Authorization: Bearer <your_token>`

---

## Request Details

### Headers

| Header        | Value               | Required | Description                              |
|---------------|---------------------|----------|------------------------------------------|
| Authorization | Bearer `<token>`    | Yes      | JWT token for the authenticated user.     |

### Body / Query Params

_No body or query parameters are required._

---

## Success Response

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    {
      "entityId": "dfe1afd5-b871-4ea3-9388-1ec130de7e5f",
      "strategyId": "98e28ed8-89dd-42b4-b290-5e4e1c095e53",
      "strategyInstanceId": "81575649-ee91-420a-9385-dac6b2a3f228",
      "strategyInstanceName": "RELIANCE",
      "strategyName": "Manual Trading BS",
      "ivObjectName": "RELIANCE",
      "instrumentId": 1010010000002885,
      "exchangeSegment": "NSECM",
      "exchangeInstrumentId": 0,
      "instrumentName": "RELIANCE"
    }
  ]
}
```
## Response Fields

| Field                   | Type     | Description                                                               |
|-------------------------|----------|---------------------------------------------------------------------------|
| `status`                | string   | Response status (e.g., `"success"`, `"error"`).                           |
| `message`               | string   | Descriptive message from the server.                                      |
| `data`                  | array    | List of rejected order objects.                                           |
| `entityId`              | string   | Unique identifier of the entity placing the order.                        |
| `strategyId`            | string   | Identifier of the strategy used for the order.                            |
| `strategyInstanceId`    | string   | Instance ID of the strategy at the time of rejection.                     |
| `strategyInstanceName`  | string   | Name of the strategy instance.                                            |
| `strategyName`          | string   | Name of the overall strategy.                                             |
| `ivObjectName`          | string   | Object or symbol name used in the strategy (e.g., "RELIANCE").            |
| `instrumentId`          | number   | Internal instrument identifier.                                           |
| `exchangeSegment`       | string   | Exchange segment (e.g., NSECM, NFO).                                      |
| `exchangeInstrumentId`  | number   | Instrument ID provided by the exchange.                                   |
| `instrumentName`        | string   | Readable name of the instrument.                                          |
