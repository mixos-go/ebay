---
title: Get_Compatibility_Properties
category: Taxonomy_API
api_name: Get_Compatibility_Properties
method: GET
path: /category_tree/{category_tree_id}/get_compatibility_properties
---

**Category:** Taxonomy_API
**API:** Get_Compatibility_Properties

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/get_compatibility_properties

## API Description
Get Compatibility Properties

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_tree_id (path) | string | Yes | This is the unique identifier of category tree. The following is the list of category_tree_id values and the eBay marketplaces that they represent. One of these ID values must be passed in as a path parameter, and the category_id value, that is passed in as query parameter, must be a valid eBay cate |
| category_id (query) | string | Yes | The unique identifier of an eBay category. This eBay category must be a valid eBay category on the specified eBay marketplace, and the category must support parts compatibility for cars, trucks, or motorcycles. The getAutomotivePartsCompatibilityPolicies method of the Selling Metadata API can be use |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityProperties | array<CompatibilityProperty> | No | This container consists of an array of all compatible vehicle properties applicable to the specified eBay marketplace and eBay category ID. |
| compatibilityProperties.name | string | No | This is the actual name of the compatible vehicle property as it is known on the specified eBay marketplace and in the eBay category. This is the string value that should be used in the compatibility_property and filter query parameters of a getCompatibilityPropertyValues request URI. Typical vehicl |
| compatibilityProperties.localizedName | string | No | This is the localized name of the compatible vehicle property. The language that is used will depend on the user making the call, or based on the language specified if the Content-Language HTTP header is used. In some instances, the string value in this field may be the same as the string in the cor |
