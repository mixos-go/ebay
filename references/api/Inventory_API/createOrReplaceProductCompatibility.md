---
title: createOrReplaceProductCompatibility
category: Inventory_API
api_name: createOrReplaceProductCompatibility
method: PUT
path: /inventory_item/{sku}/product_compatibility
---

**Category:** Inventory_API
**API:** createOrReplaceProductCompatibility

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item/{sku}/product_compatibility

## API Description
This call is used by the seller to create or replace a list of products that are compatible with the inventory item. The inventory item is identified with a SKU value in the URI. Product compatibility is currently only applicable to motor vehicle parts and accessory categories, but more categories may be supported in the future. Note: In addition to the authorization header, which is required for all Inventory API calls, this call also requires the Content-Type and Content-Language headers. See the HTTP request headers for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Language (header) | string | Yes | This header sets the natural language that will be used in the field values of the request payload. For example, the value passed in this header should be en-US for English or de-DE for German. For more information on the Content-Language header, refer to HTTP request headers . |
| sku (path) | string | Yes | This path parameter specifies the SKU (stock keeping unit) of the inventory item associated with the compatibility list being created. Use the getInventoryItems method to retrieve SKU values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| compatibleProducts | array<CompatibleProduct> | No | This container consists of an array of motor vehicles (make, model, year, trim, engine) that are compatible with the motor vehicle part or accessory specified by the sku value. |
| compatibleProducts.compatibilityProperties | array<NameValueList> | No | This container consists of an array of motor vehicles that are compatible with the motor vehicle part or accessory specified by the SKU value in the call URI. Each motor vehicle is defined through a separate set of name/value pairs. In the name field, the vehicle aspect (such as 'make', 'model', 'ye |
| compatibleProducts.compatibilityProperties.name | string | No | This string value identifies the motor vehicle aspect, such as 'make', 'model', 'year', 'trim', and 'engine'. Typically, the make, model, and year of the motor vehicle are always required, with the trim and engine being necessary sometimes, but it will be dependent on the part or accessory, and on t |
| compatibleProducts.compatibilityProperties.value | string | No | This string value identifies the motor vehicle aspect specified in the corresponding name field. For example, if the name field is 'make', this field may be 'Toyota', or if the name field is 'model', this field may be 'Camry'. The getCompatibilityPropertyValues method of the Taxonomy API can be used |
| compatibleProducts.notes | string | No | This field is used by the seller to input any notes pertaining to the compatible vehicle list being defined. The seller might use this field to specify the placement of the part on a vehicle or other applicable information. This field will only be returned if specified by the seller. Max Length : 50 |
| compatibleProducts.productFamilyProperties | ProductFamilyProperties | No | Important! The productFamilyProperties container is deprecated and should no longer be used. The compatibilityProperties container should be used instead. |
| compatibleProducts.productFamilyProperties.engine | string | No | Important! The productFamilyProperties container is no longer supported. |
| compatibleProducts.productFamilyProperties.make | string | No | Important! The productFamilyProperties container is no longer supported. |
| compatibleProducts.productFamilyProperties.model | string | No | Important! The productFamilyProperties container is no longer supported. |
| compatibleProducts.productFamilyProperties.trim | string | No | Important! The productFamilyProperties container is no longer supported. |
| compatibleProducts.productFamilyProperties.year | string | No | Important! The productFamilyProperties container is no longer supported. |
| compatibleProducts.productIdentifier | ProductIdentifier | No | This container is used in a createOrReplaceProductCompatibility call to identify a motor vehicle that is compatible with the inventory item. The user specifies either an eBay Product ID (ePID) or K-Type value to identify a vehicle, and if the motor vehicle is found in the eBay product catalog, the m |
| compatibleProducts.productIdentifier.epid | string | No | This field can be used if the seller already knows the eBay catalog product ID (ePID) associated with the motor vehicle that is to be added to the compatible product list. If this eBay catalog product ID is found in the eBay product catalog, the motor vehicle properties (e.g. make, model, year, engi |
| compatibleProducts.productIdentifier.gtin | string | No | This field can be used if the seller knows the Global Trade Item Number for the motor vehicle that is to be added to the compatible product list. If this GTIN value is found in the eBay product catalog, the motor vehicle properties (e.g. make, model, year, engine, and trim will automatically get pic |
| compatibleProducts.productIdentifier.ktype | string | No | This field can be used if the seller knows the K Type Number for the motor vehicle that is to be added to the compatible product list. If this K Type value is found in the eBay product catalog, the motor vehicle properties (e.g. make, model, year, engine, and trim) will automatically get picked up f |
| sku | string | No | The seller-defined SKU value of the inventory item that will be associated with the compatible vehicles. Note: This field is not applicable to the createOrReplaceProductCompatibility method, as the SKU value for the inventory item is passed in as part of the call URI and not in the request payload.  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| warnings | array<Error> | No | This container will be returned in a call response payload if one or more warnings or errors are triggered when an Inventory API call is made. This container will contain detailed information about the error or warning. |
| warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| warnings.domain | string | No | The name of the domain in which the error or warning occurred. |
| warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific request element(s) most closely associated to the error or warning, if any. |
| warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| warnings.message | string | No | A description of the condition that caused the error or warning. |
| warnings.outputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific response element(s) most closely associated to the error or warning, if any. |
| warnings.parameters | array<ErrorParameter> | No | Various warning and error messages return one or more variables that contain contextual information about the error or waring. This is often the field or value that triggered the error or warning. |
| warnings.parameters.name | string | No | This type contains the name and value of an input parameter that contributed to a specific error or warning condition. |
| warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
