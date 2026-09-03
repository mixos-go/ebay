---
title: getCompatibilityPropertyNames
category: Metadata_API
api_name: getCompatibilityPropertyNames
method: POST
path: /compatibilities/get_compatibility_property_names
---

**Category:** Metadata_API
**API:** getCompatibilityPropertyNames

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/compatibilities/get_compatibility_property_names

## API Description
This method is used to retrieve product compatibility property names for the specified compatibility-enabled category. Compatibility property names can be used alongside the corresponding compatibility property value (retrieved using the getCompatibilityPropertyValues method) to describe the assembly for which an item is compatible. The categoryId of the compatibility-enabled category for which to retrieve compatibility property names is required in the request body. By default, all property names within the compatibility category of the specified compatibility-enable category are returned. You can limit the size of the result set by using the dataset array to specify the types of properties you want returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See Metadata API requirements and restrictions for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of the eBay leaf category for which to retrieve compatibility property names. This category must be a valid eBay category on the specified eBay marketplace, and the category must support parts compatibility. Use the getAutomotivePartsCompatibilityPolicies method to retrieve a l |
| dataset | array<string> | No | This array defines the properties that will be returned for the compatibility-enabled category. For example, if you specify Searchable , the compatibility details will contain properties that can be used to search for products, such as make or model. Valid values: DisplayableProductDetails : Propert |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of the eBay category specified in the request. |
| properties | array<PropertyNamesResponseProperties> | No | This array contains all of the properties for the specified category. |
| properties.dataset | string | No | This field defines the types of properties are returned for the specified catalog-enabled category. Valid values: DisplayableProductDetails : Properties for use in a user interface to describe products. DisplayableSearchResults : Properties for use in results for product searches. Searchable : Prope |
| properties.propertyNames | array<PropertyNamesResponsePropertyNames> | No | This array specifies the names of the properties associated with the specified category in the specified marketplace. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. |
| properties.propertyNames.propertyDisplayName | string | No | The display name of a property. This is the localized name of the compatible property. |
| properties.propertyNames.propertyName | string | No | The canonical name of a property. This value is used as part of the name-value pairs used to specify compatibility. |
| properties.propertyNames.propertyNameMetadata | PropertyNamesResponsePropertyNameMetadata | No | The metadata for a property. |
| properties.propertyNames.propertyNameMetadata.displaySequence | integer | No | The numeric value indicating the ordering position of the property. |
