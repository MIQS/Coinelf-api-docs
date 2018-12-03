# Coinelf API

The Secure Web APIs are designed to allow client applications to access Coinelf using the HTTPS(rest) protocol over the internet.
The purpose of this document is to provide the urls and the specification of the messages communicated through Web APIs.

* [API Files](#apiFiles)
* [API General Info](#apiGeneralInfo)

<a name="apiFiles" id="apiFiles"> </a>

---
## API Files
Following API files provide the details of the APIs that are available through different access channels.

File Name                                    | Description
-------------------------------------------- | ---------------------------------------
[getting-started.md](getting-started.md)     | Getting started document before going through api documents
[wallets.md](wallets.md)                     | Details on wallets operation APIs
[pending-approvals.md](pending-approvals.md) | Details on pending approval APIs
[webhook-notifications.md](webhook-notifications.md)             | Details on notification webhook APIs
[enums.md](enums.md)                         | Details on Enum fields in the system
[error-codes.md](error-codes.md)             | Details on API error codes

<a name="apiGeneralInfo" id="apiGeneralInfo"> </a>

---
## API General Info

### Message Format
All messages are in json format.

### Message Field Types

Type         | Description
------------ | ------------
Integer      | Integer numbers
Long         | Long numbers
Boolean      | True/False
DoubleString | Decimal numbers are returned as strings to preserve full precision across platforms
Enum         | Enum definition.  Passing invalid enum values will result in API_BAD_REQUEST error
String       | Text

### Timestamp

Unless otherwise specified, all timestamps returned from API are milliseconds since UNIX Epoch.

### Mandatory Field Indicators

Indicator    | Description
------------ | ----------------------------------------
M            | Mandatory field
(M)          | Mandatory field under certain conditions
 O           | Optional field


