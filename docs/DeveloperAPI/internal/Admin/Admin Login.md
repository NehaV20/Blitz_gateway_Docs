# Admin Login API

## Overview

The **Admin Login API** is used to authenticate an admin user and generate secure **access** and **refresh tokens**. These tokens are essential for authorizing subsequent requests to protected endpoints within the admin system.

---

## Endpoint

| Method | URL                                |
|--------|-------------------------------------|
| POST   | `/api/authentication/admin/login`  |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## Request Body

```json
{
  "userName": "adminuser",
  "password": "Admin@123"
}
