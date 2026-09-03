---
title: getCompatibilityPropertyValues
category: Metadata_API
api_name: getCompatibilityPropertyValues
method: POST
path: /compatibilities/get_compatibility_property_values
---

**Category:** Metadata_API
**API:** getCompatibilityPropertyValues

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/compatibilities/get_compatibility_property_values

## API Description
This method is used to retrieve product compatibility property values associated with a single property name, in the specified category. Compatibility property values can be used alongside the corresponding compatibility property name (retrieved using the getCompatibilityPropertyNames method) to describe the assembly for which an item is compatible. The categoryId of the compatibility-enabled category for which to retrieve compatibility property values is required in the request body, as well as the propertyName for which you wish to retrieve associated values. By default, all property values associated with the specified propertyName are returned. You can limit the size of the result set by using the propertyFilter array. Only property values associated with the specified name-value pairs will be returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See Metadata API requirements and restrictions for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of the eBay leaf category for which to retrieve compatibility property values. This category must be a valid eBay category on the specified eBay marketplace, and the category must support parts compatibility. Use the getAutomotivePartsCompatibilityPolicies method to retrieve a  |
| propertyFilters | array<PropertyFilterInner> | No | This array can be used to specify the compatibility properties used limit the result set. Only values associated with the specified name-value pairs will be returned in the response. For example, if the propertyName is set to Make and the propertyValue is set to Honda , only compatible Honda vehicle |
| propertyFilters.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| propertyFilters.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| propertyFilters.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| propertyFilters.url | string | No | The URL associated with the property being described, if applicable. |
| propertyName | string | No | This field specifies the name of the property for which to retrieve associated property values. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames meth |
| sortOrder | string | No | This field specifies the sort order for the property values in the result set. Valid values: Ascending Descending Note: If no search order is specified, values are sorted in ascending order. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| metadataVersion | string | No | The version number of the metadata. This version is upticked whenever there are compatibility name changes for the specified marketplace. |
| propertyName | string | No | The name of the property specified in the request. |
| propertyValues | array<string> | No | This array specifies the property values associated with the specified propertyName , in the specified category. |
