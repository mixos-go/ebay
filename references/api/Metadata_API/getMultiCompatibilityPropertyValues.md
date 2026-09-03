---
title: getMultiCompatibilityPropertyValues
category: Metadata_API
api_name: getMultiCompatibilityPropertyValues
method: POST
path: /compatibilities/get_multi_compatibility_property_values
---

**Category:** Metadata_API
**API:** getMultiCompatibilityPropertyValues

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/compatibilities/get_multi_compatibility_property_values

## API Description
This method is used to retrieve product compatibility property values associated with multiple property names, in the specified category. Compatibility property values can be used alongside the corresponding compatibility property name (retrieved using the getCompatibilityPropertyNames method) to describe the assembly for which an item is compatible. The categoryId of the compatibility-enabled category for which to retrieve compatibility property values is required in the request body, as well as the propertyNames for which you wish to retrieve associated property values. The propertyFilter array is also required to constrain the output. Only property values associated with the specified name-value pairs will be returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See Metadata API requirements and restrictions for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of the eBay leaf category for which to retrieve property values. Use the getAutomotivePartsCompatibilityPolicies method to retrieve a list of categories that support parts compatibility. |
| propertyFilters | array<PropertyFilterInner> | No | This array can be used to specify the compatibility properties used to limit the result set. Only values associated with the specified name-value pairs will be returned in the response. For example, if the propertyName is set to Year and the propertyValue is set to 2022 , only compatible vehicles fr |
| propertyFilters.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| propertyFilters.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| propertyFilters.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| propertyFilters.url | string | No | The URL associated with the property being described, if applicable. |
| propertyNames | array<string> | No | This comma-delimited array specifies the names of the properties for which to retrieve associated property values. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilities | array<Compatibility> | No | This container defines the compatibility details associated with the specified property name value(s). |
| compatibilities.compatibilityDetails | array<CompatibilityDetails> | No | This array returns a list of compatibility details associated with the specified property name(s). |
| compatibilities.compatibilityDetails.propertyName | string | No | The name of the property being described. |
| compatibilities.compatibilityDetails.propertyValue | string | No | The value for the property specified in the propertyName field. |
| metadataVersion | string | No | The version number of the metadata. This version is upticked whenever there are compatibility name changes for the specified marketplace. |
