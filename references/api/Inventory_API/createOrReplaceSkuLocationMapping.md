---
title: createOrReplaceSkuLocationMapping
category: Inventory_API
api_name: createOrReplaceSkuLocationMapping
method: PUT
path: /listing/{listingId}/sku/{sku}/locations
---

**Category:** Inventory_API
**API:** createOrReplaceSkuLocationMapping

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/listing/{listingId}/sku/{sku}/locations

## API Description
This method allows sellers to map multiple fulfillment center locations to single-SKU listing, or to a single SKU within a multiple-variation listing. This allows eBay to leverage the location metadata associated with a seller’s fulfillment centers to calculate more accurate estimated delivery dates on their listing. Note: While location mappings can be created for listings on any eBay marketplace, the improved delivery date estimate feature is currently only supported for US-based fulfillment centers shipping domestically within the US. The listing for which the locations will be mapped is specified through the listingId and sku values associated with the item. Note that only a single SKU value can be identified; if the seller wishes to map locations to multiple/all SKU values in a multiple-variation listing, this method must be called for each of those SKUs within the listing. Note: Sellers should keep track of listingId / sku pairs that have been used for location mapping, as there is no programmatic way to retrieve or delete these pairs at this time. In the case of replacing/updating existing location mappings, this method will do a complete replacement of the location mappings associated with a SKU. This means that each existing location mappings that the seller wants to continue to associate with the SKU are required in the update call, regardless of if they are affected by the update. This method is only supported for inventory locations that have FULFILLMENT_CENTER as one of their locationTypes . For more information on fulfillment center locations, see Create a fulfillment center location . For more information on location mapping features, see Multi-warehouse program in the Selling Integration Guide. Note: Only listings with SKU values are supported. Sellers using listings creating through the Trading API can add a SKU value to their single variation listing through the Item.SKU field during listing creation or by using the ReviseItem family of calls.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingId (path) | string | Yes | This path parameter specifies the unique identifier of the listing for which multiple fulfillment center locations will be mapped to a SKU within that listing. Use the getOffers method of the Inventory API or the GetMyEbaySelling method of the Trading API to retrieve all listing IDs for all active l |
| sku (path) | string | Yes | This path parameter specifies the seller-defined SKU value of the item/variation for which multiple fulfillment center locations will be mapped. This SKU value must be defined in the listing specified in listingId parameter. Use the getOffers method of the Inventory API or the GetMyEbaySelling metho |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| locations | array<LocationAvailabilityDetails> | No | This array represents a collection of fulfillment center locations mapped to a SKU. Note: Only the first 50 locations mapped to a SKU will be considered when calculating estimated delivery dates. Sellers can set up more than 50 locations using this method, but only the first 50 locations will be con |
| locations.merchantLocationKey | string | No | The unique identifier of a seller’s fulfillment center location where inventory is available for the item or item variation. Note: When creating a location mapping using the createOrReplaceSkuLocationMapping method, the value entered in this field must be associated with a location with the FULFILLM |

## Response
_No documented response fields._
