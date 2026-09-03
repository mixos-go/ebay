---
title: createShippingFulfillment
category: Fulfillment_API
api_name: createShippingFulfillment
method: POST
path: /order/{orderId}/shipping_fulfillment
---

**Category:** Fulfillment_API
**API:** createShippingFulfillment

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/order/{orderId}/shipping_fulfillment

## API Description
When you group an order's line items into one or more packages, each package requires a corresponding plan for handling, addressing, and shipping; this is a shipping fulfillment . For each package, execute this call once to generate a shipping fulfillment associated with that package. Note: A single line item in an order can consist of multiple units of a purchased item, and one unit can consist of multiple parts or components. Although these components might be provided by the manufacturer in separate packaging, the seller must include all components of a given line item in the same package. Before using this call for a given package, you must determine which line items are in the package. If the package has been shipped, you should provide the date of shipment in the request. If not provided, it will default to the current date and time.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| orderId (path) | string | Yes | This path parameter is used to specify the unique identifier of the order associated with the shipping fulfillment being created. Use the getOrders method to retrieve order IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| lineItems | array<LineItemReference> | No | This array contains a list of or more line items and the quantity that will be shipped in the same package. |
| lineItems.lineItemId | string | No | This is the unique identifier of the eBay order line item that is part of the shipping fulfillment. Line item Ids can be found in the lineItems. lineItemId field of the getOrders response. |
| lineItems.quantity | integer | No | This is the number of lineItems associated with the trackingNumber specified by the seller. This must be a whole number greater than zero (0). Default: 1 |
| shippedDate | string | No | This is the actual date and time that the fulfillment package was shipped. This timestamp is in ISO 8601 format, which uses the 24-hour Universal Coordinated Time (UTC) clock. The seller should use the actual date/time that the package was shipped, but if this field is omitted, it will default to th |
| shippingCarrierCode | string | No | The unique identifier of the shipping carrier being used to ship the line item(s). Technically, the shippingCarrierCode and trackingNumber fields are optional, but generally these fields will be provided if the shipping carrier and tracking number are known. Note: Use the Trading API's GeteBayDetail |
| trackingNumber | string | No | The tracking number provided by the shipping carrier for this fulfillment. The seller should be careful that this tracking number is accurate since the buyer will use this tracking number to track shipment, and eBay has no way to verify the accuracy of this number. This field and the shippingCarrier |

## Response
_No documented response fields._
