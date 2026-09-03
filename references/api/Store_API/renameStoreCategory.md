---
title: renameStoreCategory
category: Store_API
api_name: renameStoreCategory
method: PUT
path: /store/categories/{category_id}
---

**Category:** Store_API
**API:** renameStoreCategory

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/store/categories/{category_id}

## API Description
This method is used to rename the single category of a user's eBay store through an asynchronous request. A successful call returns the getStoreTask URI in the Location response header. The user calls getStoreTask to retrieve the status of the rename category operation. Important! If you initiate a category change, you cannot make additional category changes until the previous change request has completed. Use getStoreTask (or getStoreTasks) method to get latest status of your last request.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_id (path) | string | Yes | The unique identifier of an eBay Store's custom category. eBay auto-generates this identifier when a seller establishes a custom store category. This category ID should not be confused with an eBay category ID. This is the category that is to be renamed. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryName | string | No | The seller-specified name of the custom category. This is the new name of the category specified through path parameter. Max Length: 35 |

## Response
_No documented response fields._
