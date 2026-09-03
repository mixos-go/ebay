---
title: deleteOffer
category: Inventory_API
api_name: deleteOffer
method: DELETE
path: /offer/{offerId}
---

**Category:** Inventory_API
**API:** deleteOffer

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/offer/{offerId}

## API Description
If used against an unpublished offer, this call will permanently delete that offer. In the case of a published offer (or live eBay listing), a successful call will either end the single-variation listing associated with the offer, or it will remove that product variation from the eBay listing and also automatically remove that product variation from the inventory item group. In the case of a multiple-variation listing, the deleteOffer will not remove the product variation from the listing if that variation has one or more sales. If that product variation has one or more sales, the seller can alternately just set the available quantity of that product variation to 0 , so it is not available in the eBay search or View Item page, and then the seller can remove that product variation from the inventory item group at a later time.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offerId (path) | string | Yes | This path parameter specifies the unique identifier of the offer being deleted. Use the getOffers method to retrieve offer IDs. |

## Response
_No documented response fields._
