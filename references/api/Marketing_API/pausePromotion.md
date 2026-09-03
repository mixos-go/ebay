---
title: pausePromotion
category: Marketing_API
api_name: pausePromotion
method: POST
path: /promotion/{promotion_id}/pause
---

**Category:** Marketing_API
**API:** pausePromotion

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/promotion/{promotion_id}/pause

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method pauses a currently-active (RUNNING) threshold discount and changes the state of the discount from RUNNING to PAUSED . Pausing a discount makes the discount temporarily unavailable to buyers and any currently-incomplete transactions will not receive the offer until the discount is resumed. Also, discount teasers are not displayed when a discount is paused. Pass the ID of the discount you want to pause using the promotion_id path parameter. Call getPromotions to retrieve the IDs of the seller's discounts. Note: You can only pause threshold discounts (you cannot pause markdown discounts).

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| promotion_id (path) | string | Yes | This path parameter takes a concatenation of the ID of the active discount being paused plus the marketplace ID on which the discount is hosted. Concatenate the two values by separating them with an "at sign" ( @ ). The ID of the discount ( promotionId ) is a unique eBay-assigned value that's genera |

## Response
_No documented response fields._
