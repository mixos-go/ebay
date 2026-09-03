---
title: getEvent
category: Deal_API
api_name: getEvent
method: GET
path: /event/{event_id}
---

**Category:** Deal_API
**API:** getEvent

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/event/{event_id}

## API Description
This method retrieves the details for an eBay event. The result set contains detailed information associated with the specified event ID, such as applicable coupons, start and end dates, and event terms. Restrictions This method can return a maximum of 10,000 items. For a list of supported sites and other restrictions, see API Restrictions . eBay Partner Network: In order to receive a commission for your sales, you must use the URL returned in the itemAffiliateWebUrl field to forward your buyer to the ebay.com site.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the eBay marketplace. See HTTP request headers for supported marketplace ID values. |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is required to support revenue sharing for eBay Partner Network and to improve the accuracy of shipping and delivery time estimations. For additional information, refer to Use request headers section of the Buying Integration Guide. |
| event_id (path) | string | Yes | This path parameters specifies the unique identifier for the eBay event being retrieved. Use the getEvents method to retrieve event IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| applicableCoupons | array<Coupon> | No | A list of coupons associated with the event. |
| applicableCoupons.redemptionCode | string | No | The coupon code. |
| applicableCoupons.terms | Terms | No | The terms of use associated with the coupon. |
| applicableCoupons.terms.fullText | string | No | A full-text description of the terms. |
| applicableCoupons.terms.summary | string | No | A summarized description of the terms. |
| description | string | No | The event description. |
| endDate | string | No | The end date for the event. |
| eventAffiliateWebUrl | string | No | The URL of the View Event page for the event, which includes the affiliate tracking ID. |
| eventId | string | No | The unique identifier for the event. |
| eventWebUrl | string | No | The web URL for the event. |
| images | array<Image> | No | The images for the event. |
| images.height | string | No | The height of the image. |
| images.imageUrl | string | No | The relative path to the image location. |
| images.text | string | No | The text associated with the image. |
| images.width | string | No | The width of the image. |
| startDate | string | No | The start date for the event. |
| terms | Terms | No | The terms associated with the event. |
| terms.fullText | string | No | A full-text description of the terms. |
| terms.summary | string | No | A summarized description of the terms. |
| title | string | No | The title of the event. |
