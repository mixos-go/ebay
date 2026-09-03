---
title: getCompatibilitiesBySpecification
category: Metadata_API
api_name: getCompatibilitiesBySpecification
method: POST
path: /compatibilities/get_compatibilities_by_specification
---

**Category:** Metadata_API
**API:** getCompatibilitiesBySpecification

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/compatibilities/get_compatibilities_by_specification

## API Description
This method is used to retrieve all compatible application name-value pairs for a part based on the provided specification(s). The part's relevant dimensions and/or characteristics can be provided through the specifications container. For example, when retrieving compatible application name-value pairs for a tire, the tire's dimensions (such as the section width or rim diameter) should be provided. By default, all compatible application name-value pairs for the specifications are returned. You can limit the size of the result set by using the compatibilityPropertyFilters array to specify the properties (such as make, model, year, or trim) you wish to be included in the response. Note: The getCompatibilityPropertyNames and getCompatibilityPropertyValues methods can be used to retrieve valid property names and values that can be used as the name-value pairs to define specifications.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See Metadata API requirements and restrictions for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The unique identifier of the eBay leaf category for which compatibility details are being retrieved. This category must be a valid eBay category on the specified eBay marketplace, and the category must support parts compatibility for cars, trucks, or motorcycles. Use the getAutomotivePartsCompatibil |
| compatibilityPropertyFilters | array<PropertyFilterInner> | No | This comma-delimited array can be used to restrict the number of compatible application name-value pairs returned in the response by specifying the properties that the seller wishes to be included in the response. Only compatible applications with the specified properties will be returned. Propertie |
| compatibilityPropertyFilters.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| compatibilityPropertyFilters.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| compatibilityPropertyFilters.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| compatibilityPropertyFilters.url | string | No | The URL associated with the property being described, if applicable. |
| dataset | string | No | This field can be used to define the type of properties that will be returned in the response. For example, if you specify Searchable , the compatibility details will contain properties that can be used to search for products, such as make or model. Note: This field cannot be used alongside dataProp |
| datasetPropertyName | array<string> | No | This comma-delimited array can be used to define the specific property name(s) that will be returned in the response. For example, if you specify Engine , the result set will only contain engines that are compatible with the input criteria. Note: This array cannot be used alongside dataset . If both |
| exactMatch | boolean | No | This boolean can be used to specify that the compatibilities returned in the response are to be defined by an exact match on the input value of specification properties. By default, an expanded compatibility match is done when it applies, such as for Load Index, where a compatible vehicle is one tha |
| paginationInput | PaginationInput | No | Important! Pagination is not yet supported by this method. If this container is included in the request, it will be ignored. |
| paginationInput.limit | integer | No | The max number of items, from the current result set, returned on a single page. Note: For getProductCompatibilities , the max value is 100. If no limit is specified, this field defaults to the max value. |
| paginationInput.offset | integer | No | The number of items that will be skipped in the result set before returning the first item in the paginated response. Combine offset with limit to control the items returned in the response. For example, if you supply an offset of 10 and a limit of 20, the first page of the response contains items 1 |
| sortOrders | array<SortOrderInner> | No | This array specifies the sorting order of the compatibility properties. Any of the searchable properties can be used to specify search order. Up to 5 levels of sort order may be specified. Note: If no sort order is specified through this field, the default sort order of popularity descending is appl |
| sortOrders.sortOrder | SortOrderProperties | No | This container is used to define the property to be used in the sorting. |
| sortOrders.sortOrder.order | string | No | Defines the order of the sort. Valid values : Ascending Descending |
| sortOrders.sortOrder.propertyName | string | No | The name of the searchable property to be used for sorting. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. |
| sortOrders.sortPriority | string | No | The priority of the specified sort order provided. For example, when a property is assigned Sort1 , its values are sorted first. Values for the property assigned Sort2 are sorted second, and so on. Valid values : Sort1 Sort2 Sort3 Sort4 Sort5 |
| specifications | array<PropertyFilterInner> | No | This array defines the specifications of the part, in the form of name-value pairs, for which compatible applications will be retrieved. |
| specifications.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| specifications.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| specifications.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| specifications.url | string | No | The URL associated with the property being described, if applicable. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityDetails | array<Compatibility> | No | This container returns the list of all compatible application name-value pairs for the given filter criteria. |
| compatibilityDetails.compatibilityDetails | array<CompatibilityDetails> | No | This array returns a list of compatibility details associated with the specified property name(s). |
| compatibilityDetails.compatibilityDetails.propertyName | string | No | The name of the property being described. |
| compatibilityDetails.compatibilityDetails.propertyValue | string | No | The value for the property specified in the propertyName field. |
| pagination | Pagination | No | Important! Not currently returned. For future use. |
| pagination.count | integer | No | The number of results showing on the current page of results. |
| pagination.limit | integer | No | The max number of entries that can be returned on a single page. |
| pagination.offset | integer | No | The number of items that will be skipped in the result set before returning the first item in the paginated response. |
| pagination.total | integer | No | The total number of results in a result set. |
