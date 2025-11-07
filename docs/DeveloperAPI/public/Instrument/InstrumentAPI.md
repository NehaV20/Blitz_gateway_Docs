# Instrument API

## Overview

The **Instrument API** is used to retrieve detailed information about various financial instruments available on the exchange. This API provides data such as instrument names, exchange, segment, strike price, expiry date, and other essential details related to the instruments.

---

## Endpoint

| Method | URL                              |
|--------|-----------------------------------|
| GET    | `/api/instruments`                |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---
## Request Body

No parameters are required for this request. Simply call the endpoint to fetch the list of all available instruments.

## Successful Response (200 OK)

```Json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": [
    {
      ...
    }
  ]
}
```
## Field Descriptions

| Field               | Type    | Description                                                             |
|---------------------|---------|-------------------------------------------------------------------------|
| status              | string  | Response status, e.g., `"success"`                                      |
| message             | string  | Message describing the outcome of the request                           |
| data                | array   | Array of instrument details                                             |

## Error Response (405 Method Not Allowed)

```Json
{
    "status": "error",
    "message": "An error occurred.",
    "error": ""
}

