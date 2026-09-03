---
title: getHandlingTimes
category: Metadata_API
api_name: getHandlingTimes
method: GET
path: /shipping/marketplace/{marketplace_id}/get_handling_times
---

**Category:** Metadata_API
**API:** getHandlingTimes

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping/marketplace/{marketplace_id}/get_handling_times

## API Description
This method retrieves a list of supported handling times for the specified marketplace. The handling time returned specifies the maximum number of business days the eBay site allows for shipping an item to domestic buyers after receiving a cleared payment. Handling times apply to both domestic and international orders. If the handling time is 1 day, the seller commits to dropping the item off for shipment one business day after payment clears. Manage handing times using business policies through the fulfillment_policy resource of the Account v1 API .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which handling times information is retrieved. See MarketplaceIdEnum for supported eBay marketplace ID values. Note: When listing the items on the French Canada, French Belgium, and Dutch Belgium marketplaces, also set the Accept-Language header |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| handlingTimes | array<ShippingHandlingTime> | No | A list of supported handling times for the marketplace. |
| handlingTimes.description | string | No | The localized description of the maximum handling time. |
| handlingTimes.extendedHandling | boolean | No | This field is only returned if its value is true . If returned, it indicates that the corresponding handling time is considered extended handling for the marketplace. Extended handling times may be used for freight shipping, but should generally be avoided if possible, as they might adversely affect |
| handlingTimes.maxHandlingTime | integer | No | The integer value returned in this field indicates the maximum number of business days that the eBay site allows as a seller's handling time measured from when the buyer pays for the order. For example, if the maxHandlingTime value is set to 1 and a buyer pays for the order on a Wednesday, the selle |
