---
title: enableInventoryLocation
category: Inventory_API
api_name: enableInventoryLocation
method: POST
path: /location/{merchantLocationKey}/enable
---

**Category:** Inventory_API
**API:** enableInventoryLocation

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/location/{merchantLocationKey}/enable

## API Description
This call enables a disabled inventory location that is specified in the merchantLocationKey path parameter. Once a disabled location is enabled, sellers can start loading/modifying inventory to that location. A successful call will return an HTTP status value of 200 OK .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| merchantLocationKey (path) | string | Yes | This path parameter specifies unique merchant-defined key (ID) for a disabled inventory location that is to be enabled. Use the getInventoryLocations method to retrieve merchant location keys. Max length : 36 |

## Response
_No documented response fields._
