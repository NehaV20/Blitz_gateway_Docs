#  Index List 

The **Index List API** returns a list of tradable index instruments available to the authenticated user. This may include major indices like NIFTY, BANKNIFTY, FINNIFTY, etc., which are typically used in watchlists or trading dashboards.

---

##  Endpoint

| Method | URL                          |
|--------|-------------------------------|
| GET    | `/api/IndexList`   |

---

##  Authentication

| Auth Type     | Required | Description                                      |
|---------------|----------|--------------------------------------------------|
| Bearer Token  | Yes       | Use a valid JWT in the Authorization header.     |

>  Use the token in the header like:  
> `Authorization: Bearer <your_token>`

---


###  Headers

| Header        | Value               | Required | Description                            |
|---------------|---------------------|----------|----------------------------------------|
| Authorization | Bearer `<token>`    | Yes      | JWT token for the authenticated user.  |

###  Body 

_No request body or query parameters are required._

---

## Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": []
}
```
##  Response Fields

| Field   | Type   | Description                                                   |
|---------|--------|---------------------------------------------------------------|
| status  | string | Response status (e.g., `"success"`, `"error"`).               |
| message | string | Descriptive message from the server.                          |
| data    | array  | List of index instrument tokens available to the user.        |

