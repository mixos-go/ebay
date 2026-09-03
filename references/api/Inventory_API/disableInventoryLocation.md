---
title: disableInventoryLocation
category: Inventory_API
api_name: disableInventoryLocation
method: POST
path: /location/{merchantLocationKey}/disable
---

**Category:** Inventory_API
**API:** disableInventoryLocation

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/location/{merchantLocationKey}/disable

## API Description
This call disables the inventory location that is specified in the merchantLocationKey path parameter. Sellers can not load/modify inventory to disabled locations. Note that disabling a location will not affect any active eBay listings associated with the disabled location, but the seller will not be able modify the offers associated with a disabled location. A successful call will return an HTTP status value of 200 OK .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| merchantLocationKey (path) | string | Yes | This path parameter specifies the unique merchant-defined key (ID) for an inventory location that is to be disabled. Use the getInventoryLocations method to retrieve merchant location keys. Max length : 36 |

## Response
_No documented response fields._
