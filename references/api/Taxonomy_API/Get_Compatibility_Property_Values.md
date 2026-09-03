---
title: Get_Compatibility_Property_Values
category: Taxonomy_API
api_name: Get_Compatibility_Property_Values
method: GET
path: /category_tree/{category_tree_id}/get_compatibility_property_values
---

**Category:** Taxonomy_API
**API:** Get_Compatibility_Property_Values

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/get_compatibility_property_values

## API Description
Get Compatibility Property Values

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_tree_id (path) | string | Yes | This is the unique identifier of the category tree. The following is the list of category_tree_id values and the eBay marketplaces that they represent. One of these ID values must be passed in as a path parameter, and the category_id value, that is passed in as query parameter, must be a valid eBay  |
| compatibility_property (query) | string | Yes | One compatible vehicle property applicable to the specified eBay marketplace and eBay category is specified in this required filter. Compatible vehicle properties are returned in the compatibilityProperties.name field of a getCompatibilityProperties response. For example, if you wanted to retrieve a |
| category_id (query) | string | Yes | The unique identifier of an eBay category. This eBay category must be a valid eBay category on the specified eBay marketplace, and the category must support parts compatibility for cars, trucks, or motorcycles. The getAutomotivePartsCompatibilityPolicies method of the Selling Metadata API can be use |
| filter (query) | string | No | One or more compatible vehicle property name/value pairs are passed in through this query parameter. The compatible vehicle property name and corresponding value are delimited with a colon (:), such as filter=Year:2018 , and multiple compatible vehicle property name/value pairs are delimited with a  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityPropertyValues | array<CompatibilityPropertyValue> | No | This array contains all compatible vehicle property values that match the specified eBay marketplace, specified eBay category, and filters in the request. If the compatibility_property parameter value in the request is 'Trim', each value returned in each value field will be a different vehicle trim, |
| compatibilityPropertyValues.value | string | No | Each value field shows one applicable compatible vehicle property value. The values that are returned will depend on the specified eBay marketplace, specified eBay category, and filters in the request. |
