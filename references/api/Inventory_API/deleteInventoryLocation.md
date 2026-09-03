---
title: deleteInventoryLocation
category: Inventory_API
api_name: deleteInventoryLocation
method: DELETE
path: /location/{merchantLocationKey}
---

**Category:** Inventory_API
**API:** deleteInventoryLocation

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/location/{merchantLocationKey}

## API Description
This call deletes the inventory location that is specified in the merchantLocationKey path parameter. Note that deleting a location will not affect any active eBay listings associated with the deleted location, but the seller will not be able modify the offers associated with the location once it is deleted. Note: Deletion is not currently supported for fulfillment center locations, as location mappings will still be retained despite the location being deleted. Instead, fulfillment center locations should be disabled using the disableInventoryLocation method. Unless one or more errors and/or warnings occur with the call, there is no response payload for this call. A successful call will return an HTTP status value of 200 OK .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| merchantLocationKey (path) | string | Yes | This path parameter specifies the unique merchant-defined key (ID) for the inventory location that is to be deleted. Use the getInventoryLocations method to retrieve merchant location keys. Max length : 36 |

## Response
_No documented response fields._
