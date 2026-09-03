---
title: moveStoreCategory
category: Store_API
api_name: moveStoreCategory
method: POST
path: /store/categories/move_category
---

**Category:** Store_API
**API:** moveStoreCategory

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/store/categories/move_category

## API Description
This method is used to move an existing user's eBay store custom category through an asynchronous request. A successful call returns the getStoreTask URI in the Location response header. The user calls getStoreTask to retrieve the status of the move category operation. Important! If you initiate a category change, you cannot make additional category changes until the previous change request has completed. Use getStoreTask (or getStoreTasks) method to get latest status of your last request.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of an eBay Store's custom category. eBay auto-generates this identifier when a seller establishes a custom store category. This category ID should not be confused with an eBay category ID. This is the category that is moved. |
| destinationParentCategoryId | string | No | The new parent category of the category to be moved is specified in this field. If the category is being moved to level 1 category, set this value to -999 . |
| listingDestinationCategoryId | string | No | This field is only needed if the category to be moved is a leaf category with listings, but a category that becomes a non-leaf category after the move. The listings of the category to be moved are moved to the category specified in this field. |

## Response
_No documented response fields._
