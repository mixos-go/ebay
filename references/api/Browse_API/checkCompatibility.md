---
title: checkCompatibility
category: Browse_API
api_name: checkCompatibility
method: POST
path: /item/{item_id}/check_compatibility
---

**Category:** Browse_API
**API:** checkCompatibility

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/item/{item_id}/check_compatibility

## API Description
This method checks if a product is compatible with the specified item. You can use this method to check the compatibility of cars, trucks, and motorcycles with a specific part listed on eBay. For example, to check the compatibility of a part, you pass in the item_id of the part as a URI parameter and specify all the attributes used to define a specific car within the compatibilityProperties container. If the call is successful, the response will be COMPATIBLE , NOT_COMPATIBLE , or UNDETERMINED . Refer to compatibilityStatus for details. Note: The only products supported are cars, trucks, and motorcycles. To find the attributes and values for a specific marketplace, you can use the compatibility methods in the Taxonomy API . You can use this data to create menus to help buyers specify the product, such as their car. For more information and a list of required attributes for the US marketplace that describe motor vehicles, refer to Check compatibility in the Buying Integration Guide . For an example, refer to the Samples section. Note: This method is supported in Sandbox but only when passing in the specified item_id and compatibility name-value pairs listed in Sample 2: Sandbox Sample . Restrictions For a list of supported sites and other restrictions, refer to API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| item_id (path) | string | Yes | This path parameter specifies the unique RESTful identifier of an item (such as the park you want to check). RESTful Item ID Format: v1 \| # \| # For a single SKU listing, pass in the item ID: v1\|2**********2\|0 For a multi-SKU listing, pass in the identifier of the variation: v1\|1**********2\|4******** |
| X-EBAY-C-MARKETPLACE-ID (header) | string | No | This header identifies the seller's eBay marketplace. It is required for all marketplaces outside of the US. Note: If the marketplace ID value is invalid or missing, the default value of EBAY_US is used. See MarketplaceIdEnum for a list of supported marketplaces. Default: EBAY_US |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers in the Using eBay RESTful APIs guide. |
| Accept-Language (header) | string | No | This header is used to indicate the natural language and locale preferred by the user for the response. This header is required when targeting a specific locale of a marketplace that supports multiple locales. For example: When targeting the French locale of the Belgium marketplace, it is required t |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityProperties | array<AttributeNameValue> | No | An array of attribute name/value pairs used to define a specific product. For example: If you wanted to specify a specific car, one of the name/value pairs would be "name" : "Year", "value" : "2019" For a list of the attributes required for cars and trucks and motorcycles see Check compatibility in  |
| compatibilityProperties.name | string | No | The name of the product attribute, such as Make , Model , Year , etc. |
| compatibilityProperties.value | string | No | The value for the name attribute, such as BMW , R1200GS , 2011 , etc. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibilityStatus | string | No | An enumeration value that tells you if the item is compatible with the product. The values are: COMPATIBLE - Indicates the item is compatible with the product specified in the request. NOT_COMPATIBLE - Indicates the item is not compatible with the product specified in the request. Be sure to check a |
| warnings | array<Error> | No | An array of warning messages. These types of errors do not prevent the method from executing but should be checked. |
| warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors , application errors , and system errors . |
| warnings.domain | string | No | The name of the primary system where the error occurred. This is relevant for application errors. |
| warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | An array of reference IDs that identify the specific request elements most closely associated to the error or warning, if any. |
| warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| warnings.message | string | No | A description of the condition that caused the error or warning. |
| warnings.outputRefIds | array<string> | No | An array of reference IDs that identify the specific response elements most closely associated to the error or warning, if any. |
| warnings.parameters | array<ErrorParameter> | No | An array of warning and error messages that return one or more variables contextual information about the error or warning. This is often the field or value that triggered the error or warning. |
| warnings.parameters.name | string | No | This is the name of input field that caused an issue with the call request. |
| warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
