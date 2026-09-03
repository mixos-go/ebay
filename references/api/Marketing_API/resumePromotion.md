---
title: resumePromotion
category: Marketing_API
api_name: resumePromotion
method: POST
path: /promotion/{promotion_id}/resume
---

**Category:** Marketing_API
**API:** resumePromotion

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/promotion/{promotion_id}/resume

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method restarts a threshold discount that was previously paused and changes the state of the discount from PAUSED to RUNNING . Only discounts that have been previously paused can be resumed. Resuming a discount reinstates the teasers and any transactions that were in motion before the discount was paused will again be eligible for the discount. Pass the ID of the discount you want to resume using the promotion_id path parameter. Call getPromotions to retrieve the IDs of the seller's discounts.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| promotion_id (path) | string | Yes | This path parameter takes a concatenation of the ID of the paused discount being resumed with the listing set plus the marketplace ID on which the discount is hosted. Concatenate the two values by separating them with an "at sign" ( @ ). The ID of the discount ( promotionId ) is a unique eBay-assign |

## Response
_No documented response fields._
