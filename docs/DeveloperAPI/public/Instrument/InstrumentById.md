# Instrument BY ID 

## Overview

The **Get Instrument BY ID API** is used to retrieve detailed information about a specific instrument using its unique `instrumentId`. This allows users to fetch comprehensive data regarding the instrument such as exchange, symbol, instrument type, and other relevant details.

---

## Endpoint

| Method | URL                                           |
|--------|-----------------------------------------------|
| GET    | `/api/instruments/{instrumentId}`             |

---

### Path Parameters

| Parameter    | Type         | Description                                         | Required |
|--------------|--------------|-----------------------------------------------------|----------|
| instrumentId | integer($int64) | Unique identifier for the instrument to retrieve  | Yes      |

---
 The `instrumentId` will be included in the URL as a path parameter.



## Successful Response (200 OK)

```Json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    ...
  }
}
```
## Response Fields

| Field               | Type   | Description                                                   |
|---------------------|--------|---------------------------------------------------------------|
| status              | string | Response status, e.g., `"success"`                           |
| message             | string | Message describing the outcome of the request                |
| data                | object | Contains the instrument data                                 |



## Error Response (401 Unauthorized)
```Json
{
  "status": "error",
  "message": "Unauthorized. Authentication is required.",
  "error": "unauthorized"
}
```
## Error Response Fields

| Field    | Type   | Description                                             |
|----------|--------|---------------------------------------------------------|
| status   | string | Error status, e.g., `"error"`                           |
| message  | string | Message describing the error                            |
| error    | string | Specific error code or message                          |
