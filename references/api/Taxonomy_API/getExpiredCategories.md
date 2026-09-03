---
title: getExpiredCategories
category: Taxonomy_API
api_name: getExpiredCategories
method: GET
path: /category_tree/{category_tree_id}/get_expired_categories
---

**Category:** Taxonomy_API
**API:** getExpiredCategories

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/get_expired_categories

## API Description
This method retrieves the mappings of expired leaf categories in the specified category tree to their corresponding active leaf categories. Note that in some cases, several expired categories are mapped to a single active category. Note: This method only returns information about categories that have been mapped (i.e., combined categories and split categories). It does not return information about expired categories that have no corresponding active categories. When a category expires in this manner, any completed items that were listed in the expired category can still be found, but new listings cannot be created in the category.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_tree_id (path) | string | Yes | The unique identifier of the eBay category tree. The category tree ID for an eBay marketplace can be retrieved using the getDefaultCategoryTreeId method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| expiredCategories | array<ExpiredCategory> | No | An array of expired category ID(s) for the requested category tree, and the currently active category ID(s) that have replaced them. |
| expiredCategories.fromCategoryId | string | No | The unique identifier of the expired eBay leaf category. |
| expiredCategories.toCategoryId | string | No | The unique identifier of the currently active eBay leaf category that has replaced the expired leaf category. Note: More than one fromCategoryID value may map into the same toCategoryID value, as multiple eBay categories may be consolidated into one new, expanded category. |
