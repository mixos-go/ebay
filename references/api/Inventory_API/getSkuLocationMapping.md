---
title: getSkuLocationMapping
category: Inventory_API
api_name: getSkuLocationMapping
method: GET
path: /listing/{listingId}/sku/{sku}/locations
---

**Category:** Inventory_API
**API:** getSkuLocationMapping

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/listing/{listingId}/sku/{sku}/locations

## API Description
This method allows sellers to retrieve the locations mapped to a specific SKU within a listing. The listingId and sku of the listing are passed in as path parameters. This method only retrieves location mappings for a single SKU value; if a seller wishes to retrieve the location mappings for all items in a multiple-variation listing, this method must be called for each variation in the listing. If there are fulfillment center locations mapped to the SKU, they will be returned in the locations array. If no locations are mapped to the SKU, status code 404 Not Found will be returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingId (path) | string | Yes | This path parameter specifies the unique identifier of the listing that the SKU belongs to for which all mapped locations will be retrieved. Use the getOffers method of the Inventory API or the GetMyEbaySelling method of the Trading API to retrieve all listing IDs for all active listings. |
| sku (path) | string | Yes | This path parameter specifies the seller-defined SKU value of the item/variation for which location mappings will be retrieved. This SKU value must be defined in the listing specified in listingId parameter Use the getOffers method of the Inventory API or the GetMyEbaySelling method of the Trading A |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| locations | array<LocationAvailabilityDetails> | No | This array represents a collection of fulfillment center locations mapped to a SKU. Note: Only the first 50 locations mapped to a SKU will be considered when calculating estimated delivery dates. Sellers can set up more than 50 locations using this method, but only the first 50 locations will be con |
| locations.merchantLocationKey | string | No | The unique identifier of a seller’s fulfillment center location where inventory is available for the item or item variation. Note: When creating a location mapping using the createOrReplaceSkuLocationMapping method, the value entered in this field must be associated with a location with the FULFILLM |
