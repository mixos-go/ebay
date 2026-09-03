---
title: addStoreCategory
category: Store_API
api_name: addStoreCategory
method: POST
path: /store/categories
---

**Category:** Store_API
**API:** addStoreCategory

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/store/categories

## API Description
This method is used to add a single new custom category to a user's eBay store through an asynchronous request. A successful call returns the getStoreTask URI in the Location response header. Call getStoreTask (or getStoreTasks ) method to retrieve the status of the add category operation. Note: Three levels of store categories are supported. Important! If you initiate a category change, you cannot make additional category changes until the previous change request has completed. Use getStoreTask (or getStoreTasks) method to get latest status of your last request.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryName | string | No | The seller-specified name of the custom category. Max Length: 35 |
| destinationParentCategoryId | string | No | This field is used to specify the parent category to which the new category belongs. To specify the new category as a top-level category, set the value of this field to -999, or just omit this field, as the default value is -999. The getStoreCategories method can be used to retrieve store category I |
| listingDestinationCategoryId | string | No | If the store category specified as the destinationParentCategoryId is a leaf category with active listings, those listings are moved to the store category identified through this listingDestinationCategoryId . If this field is omitted, the new store category being added under the parent category inh |

## Response
_No documented response fields._
