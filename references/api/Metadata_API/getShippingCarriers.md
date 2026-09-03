---
title: getShippingCarriers
category: Metadata_API
api_name: getShippingCarriers
method: GET
path: /shipping/marketplace/{marketplace_id}/get_shipping_carriers
---

**Category:** Metadata_API
**API:** getShippingCarriers

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping/marketplace/{marketplace_id}/get_shipping_carriers

## API Description
This method retrieves a list of supported shipping carriers for the specified marketplace. It provides essential information for sellers to understand which shipping carriers are available for use when listing items on that eBay marketplace. Knowing the supported carriers can help sellers optimize their shipping options and ensure efficient delivery to buyers. The value returned in the shippingCarrier field is the enumerated value required when providing shipment tracking information for that carrier. Tip: Use the getShippingServices method to explore available shipping services for each carrier. Manage shipping carriers using business policies through the fulfillment_policy resource of the Account v1 API .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which shipping carriers information is retrieved. See MarketplaceIdEnum for supported eBay marketplace ID values. Note: When listing the items on the French Canada, French Belgium, and Dutch Belgium marketplaces, also set the Accept-Language hea |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shippingCarriers | array<ShippingCarrier> | No | A list of shipping carriers available for the marketplace. |
| shippingCarriers.description | string | No | The localized description of the shipping carrier, such as UPS , FedEx , and USPS . |
| shippingCarriers.shippingCarrier | string | No | An enumerated value describing the shipping carrier returned, for example, UPS , FedEx , and USPS . These values are needed when providing shipment tracking information for each specific shipping carrier. |
