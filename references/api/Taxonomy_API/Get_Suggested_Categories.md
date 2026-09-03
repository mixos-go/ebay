---
title: Get_Suggested_Categories
category: Taxonomy_API
api_name: Get_Suggested_Categories
method: GET
path: /category_tree/{category_tree_id}/get_category_suggestions
---

**Category:** Taxonomy_API
**API:** Get_Suggested_Categories

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/get_category_suggestions

## API Description
Get Suggested Categories

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_tree_id (path) | string | Yes | The unique identifier of the eBay category tree. The category tree ID for an eBay marketplace can be retrieved using the getDefaultCategoryTreeId method. |
| q (query) | string | Yes | A quoted string that describes or characterizes the item being offered for sale. The string format is free form, and can contain any combination of phrases or keywords. eBay will parse the string and return suggested categories for the item. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categorySuggestions | array<CategorySuggestion> | No | Contains details about one or more suggested categories that correspond to the provided keywords. The array of suggested categories is sorted in order of eBay's confidence of the relevance of each category (the first category is the most relevant). Important: This call is not supported in the Sandbo |
| categorySuggestions.category | Category | No | Contains details about the suggested category. |
| categorySuggestions.category.categoryId | string | No | The unique identifier of the eBay category within its category tree. Note: The root node of a full default category tree includes the categoryId field, but its value should not be relied upon. It provides no useful information for application development. |
| categorySuggestions.category.categoryName | string | No | The name of the category identified by categoryId . |
| categorySuggestions.categoryTreeNodeAncestors | array<AncestorReference> | No | An ordered list of category references that describes the location of the suggested category in the specified category tree. The list identifies the category's ancestry as a sequence of parent nodes, from the current node's immediate parent to the root node of the category tree. Note: The root node  |
| categorySuggestions.categoryTreeNodeAncestors.categoryId | string | No | The unique identifier of the eBay ancestor category. Note: The root node of a full default category tree includes the categoryId field, but its value should not be relied upon. It provides no useful information for application development. |
| categorySuggestions.categoryTreeNodeAncestors.categoryName | string | No | The name of the ancestor category identified by categoryId . |
| categorySuggestions.categoryTreeNodeAncestors.categorySubtreeNodeHref | string | No | The href portion of the getCategorySubtree call that retrieves the subtree below the ancestor category node. |
| categorySuggestions.categoryTreeNodeAncestors.categoryTreeNodeLevel | integer | No | The absolute level of the ancestor category node in the hierarchy of its category tree. Note: The root node of any full category tree is always at level 0 . |
| categorySuggestions.categoryTreeNodeLevel | integer | No | The absolute level of the category tree node in the hierarchy of its category tree. Note: The root node of any full category tree is always at level 0 . |
| categorySuggestions.relevancy | string | No | This field is reserved for internal or future use. |
| categoryTreeId | string | No | The unique identifier of the eBay category tree from which suggestions are returned. |
| categoryTreeVersion | string | No | The version of the category tree identified by categoryTreeId . It's a good idea to cache this value for comparison so you can determine if this category tree has been modified in subsequent calls. |
