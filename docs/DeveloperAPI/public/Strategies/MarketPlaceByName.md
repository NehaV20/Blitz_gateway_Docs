The **Marketplace Strategy Details API** fetches the details of a specific strategy from the public strategy marketplace based on its name. This includes information such as ROI, drawdown, asset class, risk level, and a description of the strategy.

---

## Endpoint

| Method | URL                                        |
|--------|--------------------------------------------|
| GET    | `/api/strategies/marketPlace/{strategyName}` |

> Replace `{strategyName}` with the desired strategy name (e.g., "Nifty Rider", "BankNifty Rider").

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

Example:
```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "strategyId": "98e28ed8-89dd-42b4-b290-5e4e1c095e51",
    "strategyName": "Nifty Rider",  // This is a placeholder
    "description": "The algorithm trades Bank Nifty options by leveraging time decay, particularly in at-the-money (ATM) options, which experience the fastest rate of decay. It can run throughout the day or be used selectively in a sideways market, with higher profitability near expiry due to increased Theta decay. A straddle strategy is deployed when the index nears a round figure, aiming to capitalize on minor reversals or pauses after sharp spikes, especially when premiums are inflated. Each straddle provides a potential range of 200 points before exiting, following rebalancing rules to manage directional risk. While this strategy can yield profits in a controlled volatile market, a sharp unidirectional move may increase Implied Volatility (IV) and Gamma, causing premium inflation and potential losses.",
    "strategyType": 3,
    "riskLevel": "Moderate",
    "tags": [
      "NIFTY",
      "BANKNIFTY"
    ]
  }
}
```
### Response Fields

| Field            | Type   | Description                                                                 |
|------------------|--------|-----------------------------------------------------------------------------|
| `status`         | string | The status of the response (`"success"` or `"error"`).                     |
| `message`        | string | A message providing additional information about the request.              |
| `data`           | object | Contains the strategy details.                                              |
| `strategyId`     | string | Unique identifier for the strategy.                                        |
| `strategyName`   | string | Name of the strategy (e.g., `"Nifty Rider"`, `"BankNifty Rider"`).    |
| `description`    | string | Description of the strategy's functionality.                               |
| `strategyType`   | number | Type of the strategy (e.g., 3 might represent a particular strategy type). |
| `riskLevel`      | string | Risk level of the strategy (e.g., `"Moderate"`, `"High"`).           |
| `tags`           | array  | Tags associated with the strategy (e.g., `"NIFTY"`, `"BANKNIFTY"`).   |

