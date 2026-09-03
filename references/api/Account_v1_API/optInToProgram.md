---
title: optInToProgram
category: Account_v1_API
api_name: optInToProgram
method: POST
path: /program/opt_in
---

**Category:** Account_v1_API
**API:** optInToProgram

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/program/opt_in

## API Description
This method opts the seller in to an eBay seller program. Refer to the Account API overview for information about available eBay seller programs. Note: It can take up to 24-hours for eBay to process your request to opt-in to a Seller Program. Use the getOptedInPrograms call to check the status of your request after the processing period has passed.

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
