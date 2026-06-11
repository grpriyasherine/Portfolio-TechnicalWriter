<style>
html, body {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  color: #2c3e50;
  font-size: 16px;
  line-height: 1.7;
}

h1 { color: #1435d7; font-size: 2.2em; margin-bottom: 0.3em; }
h2 { color: #39372f; font-size: 1.45em; border-bottom: 2px solid #e8e8e8; padding-bottom: 6px; margin-top: 2em; }
h3 { display: none; }

.h3-label {
  font-size: 1em;
  font-weight: bold;
  color: #ff8000;
  margin: 1.2em 0 0.4em 0;
  display: block;
}

code {
  background: #f4f4f4;
  border-radius: 3px;
  padding: 1px 5px;
  font-family: "Courier New", monospace;
  font-size: 0.92em;
  color: #c0392b;
}

pre code {
  background: none;
  color: inherit;
  padding: 0;
}

pre {
  background: #1e1e2e;
  color: #cdd6f4;
  border-radius: 6px;
  padding: 16px 20px;
  overflow-x: auto;
  font-size: 0.9em;
  line-height: 1.6;
}

blockquote {
  background: #fffff0;
  border-left: 4px solid #1435d7;
  border-radius: 4px;
  padding: 12px 16px;
  margin: 12px 0;
  color: #2c3e50;
  font-style: italic;
}

table {
  border-collapse: collapse;
  width: 100%;
  margin: 12px 0 20px 0;
  font-size: 0.95em;
}

thead tr { background: #1435d7; color: #fff; }
thead th { padding: 10px 14px; text-align: left; font-weight: 600; font-size: 0.85em; letter-spacing: 0.4px; }
tbody tr:nth-child(even) { background: #f0f4ff; }
tbody tr:nth-child(odd)  { background: #fff; }
tbody td { padding: 9px 14px; border-top: 1px solid #e4e8f0; vertical-align: top; line-height: 1.5; }

.method-get    { background:#2471C8; color:#fff; font-weight:700; padding:3px 9px; border-radius:3px; font-family:monospace; font-size:0.82em; }
.method-post   { background:#27AE60; color:#fff; font-weight:700; padding:3px 9px; border-radius:3px; font-family:monospace; font-size:0.82em; }
.method-put    { background:#E07F1A; color:#fff; font-weight:700; padding:3px 9px; border-radius:3px; font-family:monospace; font-size:0.82em; }
.method-delete { background:#C0392B; color:#fff; font-weight:700; padding:3px 9px; border-radius:3px; font-family:monospace; font-size:0.82em; }

.s-200 { background:#D5F5E3; color:#1A6B3C; border:1px solid #A9DFBF; padding:2px 9px; border-radius:20px; font-family:monospace; font-size:0.82em; font-weight:700; }
.s-400 { background:#FDECEA; color:#922B21; border:1px solid #F5B7B1; padding:2px 9px; border-radius:20px; font-family:monospace; font-size:0.82em; font-weight:700; }
.s-404 { background:#FDECEA; color:#922B21; border:1px solid #F5B7B1; padding:2px 9px; border-radius:20px; font-family:monospace; font-size:0.82em; font-weight:700; }
.s-405 { background:#FDF2E9; color:#784212; border:1px solid #FAD7A0; padding:2px 9px; border-radius:20px; font-family:monospace; font-size:0.82em; font-weight:700; }

@media print {
  html, body { font-size: 13pt; color: #000; }
  h1, h2 { color: #000; }
}
</style>

# Petstore API Reference

> **Base URL:** `https://petstore.swagger.io/v2`
> **Resource:** `/pet`  &nbsp;|&nbsp;  **Version:** 1.0  &nbsp;|&nbsp;  **Spec:** Petstore 2.0
> **Content-Type:** `application/json`
> **Authentication:** Optional `api_key` header *(required for DELETE)*

---

**Contents**


- [Petstore API Reference](#petstore-api-reference)
  - [Overview](#overview)
  - [API Methods](#api-methods)
  - [GET /pet/{petId}](#get-petpetid)
  - [POST /pet](#post-pet)
  - [PUT /pet](#put-pet)
  - [DELETE /pet/{petId}](#delete-petpetid)
  - [HTTP Status Code Reference](#http-status-code-reference)

---

## Overview

This document provides a complete API reference for the Petstore REST API (v2). It covers all four CRUD operations on the `/pet` resource: **GET**, **POST**, **PUT**, and **DELETE**. Each section includes the endpoint URL, request parameters, request body examples, response parameters, response body examples, and error codes.

| Property | Value |
|---|---|
| **Base URL** | `https://petstore.swagger.io/v2` |
| **Content-Type** | `application/json` |
| **Authentication** | Optional `api_key` header (required for DELETE) |

<span class="h3-label">Endpoint Summary</span>

| Method | Endpoint | Description |
|---|---|---|
| <span class="method-get">GET</span> | `/pet/{petId}` | Retrieve details of a specific pet by its ID. |
| <span class="method-post">POST</span> | `/pet` | Add a new pet to the pet store. |
| <span class="method-put">PUT</span> | `/pet` | Update the details of an existing pet. |
| <span class="method-delete">DELETE</span> | `/pet/{petId}` | Permanently remove a pet record from the store. |

---

## API Methods

---

## GET /pet/{petId}

> <span class="method-get">GET</span> &nbsp; **`/pet/{petId}`** &nbsp; — &nbsp; *Retrieve a single pet by its unique identifier*

---

<span class="h3-label">Introduction</span>

This endpoint retrieves information about a single pet in the pet store, identified by its unique `petId`.

---

<span class="h3-label">Request Details</span>

| Property | Value |
|---|---|
| **Method** | `GET` |
| **Base URL** | `https://petstore.swagger.io/v2` |
| **Endpoint** | `/pet/{petId}` |

**Request URL**

```
https://petstore.swagger.io/v2/pet/{petId}
```

**Example URL**

```
https://petstore.swagger.io/v2/pet/9966
```

---

<span class="h3-label">Request Parameters</span>

| Parameter | Required / Optional | Data Type | Example Value | Description |
|---|---|---|---|---|
| `petId` | Required | Int64 | `9966` | The unique numeric identifier of the pet to retrieve. |

---

<span class="h3-label">Response Parameters</span>

| Parameter | Child Parameter | Data Type | Example Value | Description |
|---|---|---|---|---|
| `id` | — | Int64 | `9966` | Unique identifier assigned to the pet. |
| `category` | `id` | Int64 | `1` | Unique identifier of the pet category. |
| | `name` | String | `cats` | Name of the pet category. |
| `name` | — | String | `sher.cats` | Name of the pet. |
| `photoUrls` | — | String | — | URL of the pet's photo. |
| `tags` | `id` | Int64 | — | Unique identifier of the tag assigned to the pet. |
| | `name` | String | — | Name of the tag assigned to the pet. |
| `status` | — | String | `available` / `pending` / `sold` | Availability status of the pet in the store. |

---

<span class="h3-label">Example Response</span>

```json
{
  "id": 9966,
  "category": {
    "id": 1,
    "name": "cats"
  },
  "name": "sher.cats",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

---

<span class="h3-label">Error Responses</span>

| HTTP Status | Description | Common Cause |
|---|---|---|
| `400 Bad Request` | Invalid ID supplied. | The `petId` value is not a valid integer. |
| `404 Not Found` | Pet not found. | No pet exists with the specified `petId`. |




---

## POST /pet

> <span class="method-post">POST</span> &nbsp; **`/pet`** &nbsp; — &nbsp; *Add a new pet to the pet store*



<span class="h3-label">Introduction</span>

This endpoint adds a new pet to the pet store. The request body contains the pet details in JSON format. The server returns the created pet object with a confirmed status.

---

<span class="h3-label">Request Details</span>

| Property | Value |
|---|---|
| **Method** | `POST` |
| **Base URL** | `https://petstore.swagger.io/v2` |
| **Endpoint** | `/pet` |
| **Content-Type** | `application/json` |

**Request URL**

```
https://petstore.swagger.io/v2/pet
```

**Example URL**

```
https://petstore.swagger.io/v2/pet
```

---

<span class="h3-label">Request Parameters</span>

> Send all parameters in the request body as a JSON object. The `name` and `photoUrls` fields are **required**.

| Parameter | Required / Optional | Data Type | Example Value | Description |
|---|---|---|---|---|
| `id` | Optional | Int64 | `9966` | Unique identifier of the pet. The server assigns this value. |
| `category` | Optional | Object | — | Category object containing the pet species details. |
| &nbsp;&nbsp;`id` | Optional | Int64 | `1` | Unique identifier of the pet category. |
| &nbsp;&nbsp;`name` | Optional | String | `cats` | Name of the pet category. |
| `name` | **Required** | String | `sher.cats` | Name of the pet. |
| `photoUrls` | **Required** | Array | `string` | List of URLs pointing to photos of the pet. |
| `tags` | Optional | Array | — | List of tag objects assigned to the pet. |
| &nbsp;&nbsp;`id` | Optional | Int64 | `0` | Unique identifier of the tag. |
| &nbsp;&nbsp;`name` | Optional | String | `string` | Name of the tag. |
| `status` | Optional | String | `available` | Availability status of the pet. Allowed values: `available` / `pending` / `sold`. |

---

<span class="h3-label">Request Body Example</span>

```json
{
  "id": 9966,
  "category": {
    "id": 1,
    "name": "cats"
  },
  "name": "sher.cats",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

---

<span class="h3-label">Response Parameters</span>

| Parameter | Child Parameter | Data Type | Example Value | Description |
|---|---|---|---|---|
| `id` | — | Int64 | `9966` | Unique identifier assigned to the pet. |
| `category` | `id` | Int64 | `1` | Unique identifier of the pet category. |
| | `name` | String | `cats` | Name of the pet category. |
| `name` | — | String | `sher.cats` | Name of the pet. |
| `photoUrls` | — | Array | `string` | URL of the pet's photo. |
| `tags` | `id` | Int64 | `0` | Unique identifier of the tag assigned to the pet. |
| | `name` | String | `string` | Name of the tag assigned to the pet. |
| `status` | — | String | `available` | Availability status of the pet in the store. |

---

<span class="h3-label">Example Response</span>

```json
{
  "id": 9966,
  "category": {
    "id": 1,
    "name": "cats"
  },
  "name": "sher.cats",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

---

<span class="h3-label">Error Responses</span>

| HTTP Status | Description | Common Cause |
|---|---|---|
| `405 Method Not Allowed` | Invalid input. | The request body is missing or contains invalid fields. |
| `400 Bad Request` | Invalid ID supplied. | The `id` value is not a valid integer. |
| `404 Not Found` | Pet not found. | No pet exists with the specified `petId`. |

---


## PUT /pet

> <span class="method-put">PUT</span> &nbsp; **`/pet`** &nbsp; — &nbsp; *Update an existing pet*


<span class="h3-label">Introduction</span>

This endpoint updates an existing pet in the pet store. The request body contains the updated pet details in JSON format. The server returns the updated pet object with a confirmed status.

---

<span class="h3-label">Request Details</span>

| Property | Value |
|---|---|
| **Method** | `PUT` |
| **Base URL** | `https://petstore.swagger.io/v2` |
| **Endpoint** | `/pet` |
| **Content-Type** | `application/json` |

**Request URL**

```
https://petstore.swagger.io/v2/pet
```

**Example URL**

```
https://petstore.swagger.io/v2/pet
```

---

<span class="h3-label">Request Parameters</span>

> Send all parameters in the request body as a JSON object. The `name` and `photoUrls` fields are **required**.

| Parameter | Required / Optional | Data Type | Example Value | Description |
|---|---|---|---|---|
| `id` | Optional | Int64 | `9966` | Unique identifier of the pet. The server assigns this value. |
| `category` | Optional | Object | — | Category object containing the pet species details. |
| &nbsp;&nbsp;`id` | Optional | Int64 | `1` | Unique identifier of the pet category. |
| &nbsp;&nbsp;`name` | Optional | String | `string` | Name of the pet category. |
| `name` | **Required** | String | `doggie` | Name of the pet. |
| `photoUrls` | **Required** | Array | `string` | List of URLs pointing to photos of the pet. |
| `tags` | Optional | Array | — | List of tag objects assigned to the pet. |
| &nbsp;&nbsp;`id` | Optional | Int64 | `0` | Unique identifier of the tag. |
| &nbsp;&nbsp;`name` | Optional | String | `string` | Name of the tag. |
| `status` | Optional | String | `available` | Availability status of the pet. Allowed values: `available` / `pending` / `sold`. |

---

<span class="h3-label">Request Body Example</span>

```json
{
  "id": 9966,
  "category": {
    "id": 1,
    "name": "string"
  },
  "name": "doggie",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

---

<span class="h3-label">Response Parameters</span>

| Parameter | Child Parameter | Data Type | Description |
|---|---|---|---|
| `id` | — | Int64 | Unique identifier assigned to the pet. |
| `category` | `id` | Int64 | Unique identifier of the pet category. |
| | `name` | String | Name of the pet category. |
| `name` | — | String | Name of the pet. |
| `photoUrls` | — | Array | URL of the pet's photo. |
| `tags` | `id` | Int64 | Unique identifier of the tag assigned to the pet. |
| | `name` | String | Name of the tag assigned to the pet. |
| `status` | — | String | Availability status of the pet in the store. |

---

<span class="h3-label">Example Response</span>

```json
{
  "id": 9966,
  "category": {
    "id": 1,
    "name": "string"
  },
  "name": "doggie",
  "photoUrls": [
    "string"
  ],
  "tags": [
    {
      "id": 0,
      "name": "string"
    }
  ],
  "status": "available"
}
```

---

<span class="h3-label">Error Responses</span>

| HTTP Status | Description | Common Cause |
|---|---|---|
| `400 Bad Request` | Invalid ID supplied. | The `id` value is not a valid integer. |
| `404 Not Found` | Pet not found. | No pet exists with the specified `petId`. |
| `405 Method Not Allowed` | Validation exception. | The request body is missing or contains invalid fields. |

---


## DELETE /pet/{petId}

> <span class="method-delete">DELETE</span> &nbsp; **`/pet/{petId}`** &nbsp; — &nbsp; *Permanently remove a pet from the store*


<span class="h3-label">Introduction</span>

This endpoint permanently deletes a pet record from the pet store, identified by its unique `petId`. **This operation is irreversible.**

---

<span class="h3-label">Request Details</span>

| Property | Value |
|---|---|
| **Method** | `DELETE` |
| **Base URL** | `https://petstore.swagger.io/v2` |
| **Endpoint** | `/pet/{petId}` |

**Request URL**

```
https://petstore.swagger.io/v2/pet/{petId}
```

**Example URL**

```
https://petstore.swagger.io/v2/pet/9966
```

---

<span class="h3-label">Request Parameters</span>

| Parameter | Required / Optional | Data Type | Example Value | Description |
|---|---|---|---|---|
| `petId` | Required | Int64 | `9966` | The unique numeric identifier of the pet to delete. |
| `api_key` | Optional | String | — | API key passed in the request header for authentication. |

---

<span class="h3-label">Response Parameters</span>

| Parameter | Child Parameter | Data Type | Example Value | Description |
|---|---|---|---|---|
| `code` | — | Int64 | `200` | HTTP status code returned by the server. |
| `type` | — | String | `unknown` | Response type returned by the server. |
| `message` | — | String | `9966` | The `petId` of the deleted pet record. |

---

<span class="h3-label">Example Response</span>

```json
{
  "code": 200,
  "type": "unknown",
  "message": "9966"
}
```

---

<span class="h3-label">Error Responses</span>

| HTTP Status | Description | Common Cause |
|---|---|---|
| `400 Bad Request` | Invalid ID supplied. | The `petId` value is not a valid integer. |
| `404 Not Found` | Pet not found. | No pet exists with the specified `petId`. |

---

## HTTP Status Code Reference

The following HTTP status codes may be returned by any endpoint in this API.

| HTTP Status Code | Status Text | Applies To | Description |
|---|---|---|---|
| `200` | OK | GET · POST · PUT · DELETE | The request succeeds. The response body contains the result. |
| `400` | Bad Request | GET · PUT · DELETE | The request contains an invalid `petId`. Supply a valid integer. |
| `404` | Not Found | GET · PUT · DELETE | No pet record exists for the given `petId`. Verify the ID and retry. |
| `405` | Method Not Allowed | POST · PUT | The request body is missing or contains invalid fields. |

---

<div align="center">

*&nbsp; petstore.swagger.io/v2 &nbsp;|&nbsp; Version 1.0 &nbsp;|&nbsp; Petstore 2.0*

</div>
