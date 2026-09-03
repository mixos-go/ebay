---
title: deleteItemPriceMarkdownPromotion
category: Marketing_API
api_name: deleteItemPriceMarkdownPromotion
method: DELETE
path: /item_price_markdown/{promotion_id}
---

**Category:** Marketing_API
**API:** deleteItemPriceMarkdownPromotion

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/item_price_markdown/{promotion_id}

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method deletes the item price markdown discount specified by the promotion_id path parameter. Call getPromotions to retrieve the IDs of a seller's discounts. You can delete any discount with the exception of those that are currently active (RUNNING). To end a running discount, call updateItemPriceMarkdownPromotion and adjust the endDate field as appropriate.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| promotion_id (path) | string | Yes | This path parameter takes a concatenation of the ID of the discount you want to delete plus the marketplace ID on which the discount is hosted. Concatenate the two values by separating them with an "at sign" ( @ ). The ID of the discount ( promotionId ) is a unique eBay-assigned value that's generat |

## Response
_No documented response fields._
