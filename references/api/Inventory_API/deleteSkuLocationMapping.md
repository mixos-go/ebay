---
title: deleteSkuLocationMapping
category: Inventory_API
api_name: deleteSkuLocationMapping
method: DELETE
path: /listing/{listingId}/sku/{sku}/locations
---

**Category:** Inventory_API
**API:** deleteSkuLocationMapping

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/listing/{listingId}/sku/{sku}/locations

## API Description
This method allows sellers to remove all location mappings associated with a specific SKU within a listing. The listingId and sku of the listing are passed in as path parameters. Important! To remove all location mappings from a multiple-variation listing, this method must be used for each individual SKU in the listing.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingId (path) | string | Yes | This path parameter specifies the unique identifier of the listing that the SKU belongs to for which all mapped locations will be removed. Use the getOffers method of the Inventory API or the GetMyEbaySelling method of the Trading API to retrieve all listing IDs for all active listings. |
| sku (path) | string | Yes | This path parameter specifies the seller-defined SKU value of the item/variation for which location mappings will be removed. This SKU value must be defined in the listing specified in listingId parameter Use the getOffers method of the Inventory API or the GetMyEbaySelling method of the Trading API |

## Response
_No documented response fields._
