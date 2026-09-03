---
title: optOutOfProgram
category: Account_v1_API
api_name: optOutOfProgram
method: POST
path: /program/opt_out
---

**Category:** Account_v1_API
**API:** optOutOfProgram

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/program/opt_out

## API Description
This method opts the seller out of a seller program in which they are currently opted in to. A seller can retrieve a list of the seller programs they are opted-in to using the getOptedInPrograms method.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| programType | string | No | The seller program to opt in to when part of an optInToProgram request, or out of when part of an optOutOfProgram request. When returned in an getOptedInPrograms response, a separate programType field is returned for each seller program that the seller is opted in to. For implementation help, refer  |

## Response
_No documented response fields._
