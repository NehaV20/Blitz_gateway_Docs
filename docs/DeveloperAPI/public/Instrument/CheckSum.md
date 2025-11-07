#  Check Sum 

##  Overview

TThe **Check Sum API** allows clients to detect whether the Instrument Master file has been updated on the server.
This API is designed to avoid unnecessary downloads of the instrument data. By comparing the current checksum from the server with a previously stored checksum, you can:

 Skip download if data hasn't changed (saves time & resources).

 Download and update if data has changed (ensures accuracy).



---

##  Endpoint

| Method | URL                         |
|--------|------------------------------|
| GET    | `/api/instruments/checkSum` |

---

##  Parameters

### Query Parameters

_None required._

---

##  Request Headers

| Header        | Value              | Required |
|---------------|--------------------|----------|
| Content-Type  | `application/json` |  Yes   |
| Accept        | `*/*`              |  Yes   |

---

##  Successful Response (200 OK)

```json
{
  "status": "success",
  "message": "Request processed successfully.",
  "data": "<checksum_value>"
}
```
##  Response Fields

| Field   | Type   | Description                                                                 |
|---------|--------|-----------------------------------------------------------------------------|
| status  | string | Status of the API response (e.g., `"success"` or `"error"`)                 |
| message | string | A short message confirming the result of the request                        |
| data    | string | The checksum value for the instrument file. Used to detect data changes.    |
