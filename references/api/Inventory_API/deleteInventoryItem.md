---
title: deleteInventoryItem
category: Inventory_API
api_name: deleteInventoryItem
method: DELETE
path: /inventory_item/{sku}
---

**Category:** Inventory_API
**API:** deleteInventoryItem

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item/{sku}

## API Description
This call is used to delete an inventory item record associated with a specified SKU. A successful call will not only delete that inventory item record, but will also have the following effects: Delete any and all unpublished offers associated with that SKU; Delete any and all single-variation eBay listings associated with that SKU; Automatically remove that SKU from a multiple-variation listing and remove that SKU from any and all inventory item groups in which that SKU was a member. The authorization header is the only required HTTP header for this call. See the HTTP request headers section for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | This path parameter specifies the seller-defined SKU value of the product whose inventory item record you wish to delete. Use the getInventoryItems method to retrieve SKU values. Max length : 50 |

## Response
_No documented response fields._
