---
id: response-structure
title: Response Structure
sidebar_label: Response Structure
description: Understand the standard API response format from Blitz Gateway.
---

# API Response Structure

This section documents the structure of both successful and error responses returned by the Blitz Gateway API.

---

##  Successful Response (200 OK)

Returned when the API request completes successfully.

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": {
    "accessToken": "<JWT_ACCESS_TOKEN>",
    "refreshToken": "<JWT_REFRESH_TOKEN>",
    "marketDataApiKey": null
  }
}
```


---

## Error Response (500 Internal Server Error)

```json
{
  "status": "error",
  "message": "Internal server error. An error occurred on the server.",
  "error": "internal server error"
}
```

##  Response Fields

| Field                    | Type           | Description                                                                 |
|--------------------------|----------------|-----------------------------------------------------------------------------|
| `status`                | `string`       | Status of the API response. Can be:<br/>`success` for successful requests.<br/>`error` for failed requests. |
| `message`               | `string`       | Describes the outcome of the request.<br/>E.g., `"Request processed successfully."` |
| `data.accessToken`      | `string`       | JWT token used for authenticating future API calls. |
| `data.refreshToken`     | `string`       | JWT token used to refresh the access token. |
| `data.marketDataApiKey` | `string/null`  | Reserved for future use.<br/>Currently returns `null`. |
| `error`                 | `string`       | Only in error responses.<br/>Provides details of the issue (e.g., `"internal server error"`). |
