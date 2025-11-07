---
id: request-structure
title: Request Structure
sidebar_label: Request Structure
description: Learn how to structure API requests to Blitz Gateway.
---

#  Request Structure

Use the following structure to make HTTP requests to the Blitz Gateway API:

```bash
curl -X [API_METHOD] \
  'http://[BASE_URL]/api/[API_ENDPOINT]' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer [YOUR_ACCESS_TOKEN]' \
  [CONTENT_TYPE_HEADER] \
  [REQUEST_PAYLOAD]
```

  
---

##  Placeholders 

| Placeholder             | Description                                                                 |
|-------------------------|-----------------------------------------------------------------------------|
| `[API_METHOD]`          | The HTTP method for your request (e.g., `GET`, `POST`, `PUT`, `DELETE`).    |
| `[API_ENDPOINT]`        | The specific API endpoint you're targeting (e.g., `/user/profile`).         |
| `[YOUR_ACCESS_TOKEN]`   | Your personal access token for authentication.                              |
| `[CONTENT_TYPE_HEADER]` | Use:<br/>`-H "Content-Type: application/json"` for JSON payloads.<br/>`-H "Content-Type: application/x-www-form-urlencoded"` for form data.<br/>Omit if not applicable. |
| `[REQUEST_PAYLOAD]`     | For `POST` and `PUT` methods with data, use:<br/>`-d '[YOUR_JSON_DATA]'`. <br/>Omit for `GET` or `DELETE` methods. |

