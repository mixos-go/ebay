---
title: getEvents
category: Deal_API
api_name: getEvents
method: GET
path: /event
---

**Category:** Deal_API
**API:** getEvents

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/event

## API Description
This method returns paginated results containing all eBay events for the specified marketplace. Restrictions This method can return a maximum of 10,000 items. For a list of supported sites and other restrictions, see API Restrictions . eBay Partner Network: In order to receive a commission for your sales, you must use the URL returned in the itemAffiliateWebUrl field to forward your buyer to the ebay.com site.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | The maximum number of items, from the current result set, returned on a single page. Default: 20 Maximum Value: 100 |
| offset (query) | string | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the eBay marketplace. See HTTP request headers for supported marketplace ID values. |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is required to support revenue sharing for eBay Partner Network and to improve the accuracy of shipping and delivery time estimations. For additional information, refer to Use request headers section of the Buying Integration Guide. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| events | array<Event> | No | A list of results that match the search criteria. |
| events.applicableCoupons | array<Coupon> | No | A list of coupons associated with the event. |
| events.applicableCoupons.redemptionCode | string | No | The coupon code. |
| events.applicableCoupons.terms | Terms | No | The terms of use associated with the coupon. |
| events.applicableCoupons.terms.fullText | string | No | A full-text description of the terms. |
| events.applicableCoupons.terms.summary | string | No | A summarized description of the terms. |
| events.description | string | No | The event description. |
| events.endDate | string | No | The end date for the event. |
| events.eventAffiliateWebUrl | string | No | The URL of the View Event page for the event, which includes the affiliate tracking ID. |
| events.eventId | string | No | The unique identifier for the event. |
| events.eventWebUrl | string | No | The web URL for the event. |
| events.images | array<Image> | No | The images for the event. |
| events.images.height | string | No | The height of the image. |
| events.images.imageUrl | string | No | The relative path to the image location. |
| events.images.text | string | No | The text associated with the image. |
| events.images.width | string | No | The width of the image. |
| events.startDate | string | No | The start date for the event. |
| events.terms | Terms | No | The terms associated with the event. |
| events.terms.fullText | string | No | A full-text description of the terms. |
| events.terms.summary | string | No | A summarized description of the terms. |
| events.title | string | No | The title of the event. |
| href | string | No | The relative path to the current set of results. |
| limit | integer | No | The maximum number of items, from the current result set, returned on a single page. Default: 20 |
| next | string | No | The relative path to the next set of results. |
| offset | integer | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| prev | string | No | The relative path to the previous set of results. |
| total | integer | No | The total number of matches for the specified search criteria. |
