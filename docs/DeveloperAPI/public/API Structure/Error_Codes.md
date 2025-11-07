---
id: error-codes
title: Error Codes
sidebar_label: Error Codes
description: List of standard HTTP and application-specific error codes used in Blitz Gateway.
---

# Error Codes

The Blitz Gateway API follows standard HTTP status codes to indicate the result of your API requests. Below is a list of possible error codes and their descriptions.

---

##  HTTP Error Codes

These codes represent issues that can occur when making requests to the server. They help identify the type of problem that occurred.

| Error Code | Name                   | Description                                                                 |
|------------|------------------------|-----------------------------------------------------------------------------|
| `400`      | Bad Request            | The server could not understand the request due to invalid syntax or missing parameters. |
| `401`      | Unauthorized           | Authentication failed. Your API key is missing, invalid, or expired.       |
| `403`      | Forbidden              | You do not have permission to access the requested resource.               |
| `404`      | Not Found              | The requested resource could not be found on the server.                   |
| `405`      | Method Not Allowed     | The HTTP method used is not supported for the requested endpoint.          |
| `406`      | Not Acceptable         | The server cannot return a response matching the requested content type (usually JSON). |
| `410`      | Gone                   | The requested resource is no longer available and has been permanently removed. |
| `429`      | Too Many Requests      | Rate limit exceeded. Reduce the frequency of your requests.                |
| `500`      | Internal Server Error  | An unexpected error occurred on the server. Please try again later.        |
| `503`      | Service Unavailable    | The server is currently undergoing maintenance or is temporarily unavailable. |

---

