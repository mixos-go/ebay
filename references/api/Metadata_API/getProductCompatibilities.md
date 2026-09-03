---
title: getProductCompatibilities
category: Metadata_API
api_name: getProductCompatibilities
method: POST
path: /compatibilities/get_product_compatibilities
---

**Category:** Metadata_API
**API:** getProductCompatibilities

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/compatibilities/get_product_compatibilities

## API Description
This method is used to retrieve all available item compatibility details for the specified product. Item compatibility details can be used to see the properties for which an item is compatible. For example, if you are searching for a part for a specific vehicle, you can use this method to see the years, engine, and/or trim for which the part is compatible. Item compatibility details are returned as name-value pairs. The product for which to retrieve item compatibility details must be provided through the productIdentifier field. This value can be either an eBay specific identifier (such as an ePID) or an external identifier (such as a UPC). By default, all available item compatibility details for the specified product are returned. You can limit the size of the result set using the dataset or datasetPropertyName fields to specify the types of properties you want returned in the response. The applicationPropertyFilter array can also be used so that only parts compatible with the specified name-value pairs are returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See Metadata API requirements and restrictions for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| applicationPropertyFilters | array<PropertyFilterInner> | No | This array is used to filter the properties of an application, such as a vehicle's make or model, that will be returned in the response. Application property filters are specified as name-value pairs. Only products compatible with these name-value pairs will be returned. |
| applicationPropertyFilters.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| applicationPropertyFilters.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| applicationPropertyFilters.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| applicationPropertyFilters.url | string | No | The URL associated with the property being described, if applicable. |
| dataset | array<string> | No | This array defines the type of properties that are returned for the catalog-enabled category. For example, if you specify Searchable , the compatibility details will contain properties that can be used to search for products, such as make or model. Note: This field cannot be used alongside dataPrope |
| datasetPropertyName | array<string> | No | This comma-delimted array can be used to define the specific property name(s) that will be returned in the response. For example, if you specify Engine , the result set will only contain engines that are compatible with the input criteria. Note: This array cannot be used alongside dataset . If both  |
| disabledProductFilter | DisabledProductFilter | No | This container can be used to specify whether or not to filter out products which are disabled for selling on eBay and/or disabled for product review. |
| disabledProductFilter.excludeForEbayReviews | boolean | No | Specifies whether to filter out products excluded for eBay reviews. If set to true , items excluded from eBay reviews are not returned. |
| disabledProductFilter.excludeForEbaySelling | boolean | No | Specifies whether to filter out products excluded for eBay selling. If set to true , items excluded from eBay selling are not returned. |
| paginationInput | PaginationInput | No | This container controls the pagination of the result set. |
| paginationInput.limit | integer | No | The max number of items, from the current result set, returned on a single page. Note: For getProductCompatibilities , the max value is 100. If no limit is specified, this field defaults to the max value. |
| paginationInput.offset | integer | No | The number of items that will be skipped in the result set before returning the first item in the paginated response. Combine offset with limit to control the items returned in the response. For example, if you supply an offset of 10 and a limit of 20, the first page of the response contains items 1 |
| productIdentifier | ProductIdentifier | No | This container is used to provide unique identifier for the product. The product identifier consists of an identifier type and value, and are unique across all sites. |
| productIdentifier.ean | string | No | The EAN of the item, if applicable. EAN is the European Article Number, a barcode standard for retail product labeling primarily used outside of North America. |
| productIdentifier.epid | string | No | The ePID (eBay Product Identifier) of the item, if applicable. ePID is a unique identifier used by eBay to track products in its catalog. Use the getProduct method of the Catalog API to retrieve the ePID of an item. |
| productIdentifier.isbn | string | No | The ISBN of the item, if applicable. ISBN is the International Standard Book Number, a unique identifier for books. |
| productIdentifier.productId | string | No | The product ID of the item, if applicable. The product ID is a general term for a unique identifier assigned to a product. |
| productIdentifier.upc | string | No | The UPC of the item, if applicable. UPC stands for Universal Product Code, a unique identifier for products, primarily in North America. |
| sortOrders | array<SortOrderInner> | No | This array controls the sort order of compatibility properties. |
| sortOrders.sortOrder | SortOrderProperties | No | This container is used to define the property to be used in the sorting. |
| sortOrders.sortOrder.order | string | No | Defines the order of the sort. Valid values : Ascending Descending |
| sortOrders.sortOrder.propertyName | string | No | The name of the searchable property to be used for sorting. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. |
| sortOrders.sortPriority | string | No | The priority of the specified sort order provided. For example, when a property is assigned Sort1 , its values are sorted first. Values for the property assigned Sort2 are sorted second, and so on. Valid values : Sort1 Sort2 Sort3 Sort4 Sort5 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityDetails | array<ProductResponseCompatibilityDetails> | No | This container provides compatibility details for the specified product. |
| compatibilityDetails.noteDetails | array<PropertyFilterInner> | No | This array returns additional comments about the corresponding product in the form of name-value pairs. |
| compatibilityDetails.noteDetails.propertyName | string | No | The name of the property being described. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. Use the getCompatibilityPropertyNames method to retrieve valid property names for a specified ca |
| compatibilityDetails.noteDetails.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is Make , then the propertyValue will be the specific make of the vehicle, such as Toyota . Use the getCompatibilityPropertyValues to retreive valid property values associated with a specified property na |
| compatibilityDetails.noteDetails.unitOfMeasurement | string | No | The unit of measurement of the property being described, if applicable. |
| compatibilityDetails.noteDetails.url | string | No | The URL associated with the property being described, if applicable. |
| compatibilityDetails.productDetails | array<PropertyValues> | No | This array returns details about the product in the form of name-value pairs. |
| compatibilityDetails.productDetails.propertyName | string | No | The name of the property. For example, typical vehicle property names are 'Make', 'Model', 'Year', 'Engine', and 'Trim', but will vary based on the eBay marketplace and the eBay category. |
| compatibilityDetails.productDetails.propertyValue | string | No | The value for the property specified in the properyName field. For example, if the propertyName is make , then the propertyValue will be the specific make of the vehicle, such as Toyota . |
| pagination | Pagination | No | This container returns the pagination settings for the result set. |
| pagination.count | integer | No | The number of results showing on the current page of results. |
| pagination.limit | integer | No | The max number of entries that can be returned on a single page. |
| pagination.offset | integer | No | The number of items that will be skipped in the result set before returning the first item in the paginated response. |
| pagination.total | integer | No | The total number of results in a result set. |
