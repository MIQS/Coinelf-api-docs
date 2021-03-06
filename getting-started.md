# Getting Started

* [Base Url](#baseUrl)
* [Success/Error Response](#response)
* [Pagination](#pagination)
* [Authentication](#authentication)
* [Supported Coins](#coins)

<a name="baseUrl" id="baseUrl"> </a>
---
## Base Url and Message Format

https://www.coinelf.io/v1/api

All requests and responses use application/json content type. Responses	follow HTTP response status codes to indicate
the success and the failure.

<a name="response" id="response"> </a>
---
## Success/Error Response

Successful http response contains HTTP status code 200 and an optional body. If the response contains the body,
the fields within the body are documented in each related API sections.  Failed http response contains non 200 HTTP status
code and the body with an errorCode field to indicate the cause of the failures.

### Error Response Fields

Name         | Type        | Mandatory | Description
------------ | ------------| ----------| -----------------------------------------------------------------------------------------
errorCode    | String      | M         | Error code. e.g.INVALID_PASSWORD
errorData    | String      | O         | Additional information on the user data that may cause the error.  Data is provided in json format.

<a name="pagination" id="pagination"> </a>
---
## Pagination

Pagination is supported for all REST calls that return arrays. The newest items are returned by default.

Name	   | Type(value)| Mandatory| Description
-----------| -----------|----------|-------------------
pageNumber | Integer    | O        | Default to 1
pageSize   | Integer    | O	       | Default to 100

Example: GET transfers?pageNumber=1&pageSize=100

<a name="authentication" id="authentication"> </a>
---
## Authentication
All requests to endpoints require authentication by providing API key, signature, timestamp and passcode.

### API Key
Before being able to send any requests, you must create API key via the coinelf website. Upon creation, you will be provided
* Key  (Generated by coinelf)
* Secret  (Generated by coinelf)
* Passcode  (Provided by user and coinelf stores the salted hash of the passcode to further secure the api access)

### API Key Permissions
You can restrict the following access levels of API keys under coin level
+ VIEW

+ SPEND

+ ADMIN

### Sending a Request

All requests must contain the following headers:
* API-KEY The api key
* API-SIGN The base64-encoded signature by creating a sha256 HMAC using the base64 decoded secret Key on the prehash string timestamp + method + url and base64-encode the output
* API-PASSCODE The passcode provided during api key creation

<a name="coins" id="coins"> </a>
---
## Supported Coins

Coinelf supports the following digital assets

Id   	   | Digital Asset
-----------| --------------
BTC        | Bitcoin
USDT       | Tether
