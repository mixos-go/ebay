---
title: updateNegativeKeyword
category: Marketing_API
api_name: updateNegativeKeyword
method: PUT
path: /negative_keyword/{negative_keyword_id}
---

**Category:** Marketing_API
**API:** updateNegativeKeyword

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/negative_keyword/{negative_keyword_id}

## API Description
This method updates the status of an existing negative keyword. Specify the negative_keyword_id as a path parameter, and specify the negativeKeywordStatus in the request body.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| negative_keyword_id (path) | string | Yes | The unique identifier for the negative keyword. This value is returned in the Location response header from the createNegativeKeyword method. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| negativeKeywordStatus | string | No | A field that defines the status of the negative keyword. For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
