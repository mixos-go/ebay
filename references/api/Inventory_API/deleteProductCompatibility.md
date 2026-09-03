---
title: deleteProductCompatibility
category: Inventory_API
api_name: deleteProductCompatibility
method: DELETE
path: /inventory_item/{sku}/product_compatibility
---

**Category:** Inventory_API
**API:** deleteProductCompatibility

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item/{sku}/product_compatibility

## API Description
This call is used by the seller to delete the list of products that are compatible with the inventory item that is associated with the compatible product list. The inventory item is identified with a SKU value in the URI. Product compatibility is currently only applicable to motor vehicle parts and accessory categories, but more categories may be supported in the future.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | This path parameter specifies the SKU (stock keeping unit) of the inventory item that is associated with the product compatibility list that is being deleted. Use the getInventoryItems method to retrieve SKU values. |

## Response
_No documented response fields._
