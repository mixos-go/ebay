---
title: deleteStoreCategory
category: Store_API
api_name: deleteStoreCategory
method: DELETE
path: /store/categories/{category_id}
---

**Category:** Store_API
**API:** deleteStoreCategory

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/store/categories/{category_id}

## API Description
This method is used to delete one custom category of a user's eBay store through an asynchronous request. A successful call returns the getStoreTask URI in the Location response header. Call getStoreTask (or getStoreTasks ) method to retrieve the status of the delete category operation. Important! If you initiate a category change, you cannot make additional category changes until the previous change request has completed. Use getStoreTask (or getStoreTasks) method to get latest status of your last request.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_id (path) | string | Yes | The unique identifier of an eBay Store's custom category. eBay auto-generates this identifier when a seller establishes a custom store category. This category ID should not be confused with an eBay category ID. The getStoreCategories method can be used to retrieve store category IDs. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingDestinationCategoryId | string | No | This field is only needed if the category to be deleted or any of its children categories have one or more active listings. The operation will fail otherwise. All active listings in or under the category to be deleted will be moved to the store category specified in this field. The getStoreCategorie |

## Response
_No documented response fields._
