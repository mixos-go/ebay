---
title: getProductCompatibility
category: Inventory_API
api_name: getProductCompatibility
method: GET
path: /inventory_item/{sku}/product_compatibility
---

**Category:** Inventory_API
**API:** getProductCompatibility

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item/{sku}/product_compatibility

## API Description
This call is used by the seller to retrieve the list of products that are compatible with the inventory item. The SKU value for the inventory item is passed into the call URI, and a successful call with return the compatible vehicle list associated with this inventory item. Product compatibility is currently only applicable to motor vehicle parts and accessory categories, but more categories may be supported in the future.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | This path parameter specifies the SKU (stock keeping unit) of the inventory item associated with the product compatibility list being retrieved. Use the getInventoryItems method to retrieve SKU values. |

## Response
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
