---
title: Get_a_Default_Category_Tree_ID
category: Taxonomy_API
api_name: Get_a_Default_Category_Tree_ID
method: GET
path: /get_default_category_tree_id
---

**Category:** Taxonomy_API
**API:** Get_a_Default_Category_Tree_ID

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/get_default_category_tree_id

## API Description
Get a Default Category Tree ID

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (query) | string | Yes | The unique identifier of the eBay marketplace for which the category tree ID is requested. For a list of supported marketplace IDs, see Marketplaces with Default Category Trees . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTreeId | string | No | The unique identifier of the eBay category tree for the specified marketplace. |
| categoryTreeVersion | string | No | The version of the category tree identified by categoryTreeId . It's a good idea to cache this value for comparison so you can determine if this category tree has been modified in subsequent calls. |
