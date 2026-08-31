# REST API — cURL

This guide provides a quick reference for interacting with REST APIs using cURL. It covers the five commonly used HTTP methods - POST, GET, PUT, PATCH, and DELETE, along with common cURL options for headers, request bodies, and cookie-based session authentication.

## POST — Create

```bash
curl -s -k -X POST "https://<API-URL>/resource" \
  -H "Content-Type: application/json" \
  -d '{"name":"example"}'
```

## GET — Retrieve

```bash
curl -s -k -X GET "https://<API-URL>/resource"
```

## PUT — Update/Replace

```bash
curl -s -k -X PUT "https://<API-URL>/resource" \
  -H "Content-Type: application/json" \
  -d '{"name":"example","status":"active"}'
```

## PATCH — Partially Update

```bash
curl -s -k -X PATCH "https://<API-URL>/resource" \
  -H "Content-Type: application/json" \
  -d '{"status":"inactive"}'
```

## DELETE — Delete

```bash
curl -s -k -X DELETE "https://<API-URL>/resource"
```

## Cookies

### `-c` — Save Cookies

Save cookies received from the server to a file:

```bash
curl -s -k -X POST "https://<API-URL>/login" \
  -H "Content-Type: application/json" \
  -d @credentials.json \
  -c cookie.txt
```

### `-b` — Send Cookies

Send previously saved cookies with a request:

```bash
curl -s -k -X GET "https://<API-URL>/resource" \
  -b cookie.txt
```

## Request Body from a File

Instead of putting data directly after `-d`, a file can be used:

```bash
curl -s -k -X POST "https://<API-URL>/resource" \
  -H "Content-Type: application/json" \
  -d @config.json
```

## cURL Options

| Option | Purpose                           |
| ------ | --------------------------------- |
| `-s`   | Silent                            |
| `-k`   | Skip TLS certificate verification |
| `-X`   | Specify HTTP method               |
| `-H`   | Add HTTP header                   |
| `-d`   | Send request body/data            |
| `-c`   | Save cookies to a file            |
| `-b`   | Send cookies from a file          |

## HTTP Methods

| Method   | Purpose                                   |
| -------- | ----------------------------------------- |
| `POST`   | Create a resource or perform an operation |
| `GET`    | Retrieve a resource                       |
| `PUT`    | Update or replace a resource              |
| `PATCH`  | Partially update a resource               |
| `DELETE` | Delete a resource                         |
