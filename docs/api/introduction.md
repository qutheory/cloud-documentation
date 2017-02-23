# API Introduction

The Vapor Cloud API is a great way to automate tasks in Vapor Cloud.

Our APIs use a REST based architecture, and will live up to the
standards in REST.

Whenever you need to send data to the API, this should be in JSON format
in the payload of the request.

## Base URL

You should always call APIs with the following base URL:

```
https://api.vapor.cloud
```

## Authentication

Before making requests, make sure to optain a TOKEN. We use JWT (JSON
Web Token).

You find login/create etc. In the Admin API documentation. The token
lasts for 15 minutes, and need to be renewed by making a call to the
renew endpoint with the renew token provided by the login call.

The renew token lasts for 7 days
