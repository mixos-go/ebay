---
title: getShippingLocations
category: Metadata_API
api_name: getShippingLocations
method: GET
path: /shipping/marketplace/{marketplace_id}/get_shipping_locations
---

**Category:** Metadata_API
**API:** getShippingLocations

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping/marketplace/{marketplace_id}/get_shipping_locations

## API Description
This method retrieves a list of supported shipping locations for the specified marketplace. It provides sellers with information on where they can ship their items. Sellers can use this information to configure their shipping settings. Tip: Use the getExcludeShippingLocations method to return locations where the seller does not ship. Manage shipping locations using business policies through the fulfillment_policy resource of the Account v1 API .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which shipping locations information is retrieved. See MarketplaceIdEnum for supported eBay marketplace ID values. Note: When listing the items on the French Canada, French Belgium, and Dutch Belgium marketplaces, also set the Accept-Language he |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shippingLocations | array<ShippingLocation> | No | The complete list of geographical regions, countries, domestic areas, and special locations for the specified eBay marketplace that can be set as shipping locations. |
| shippingLocations.description | string | No | The localized location name. |
| shippingLocations.shippingLocation | string | No | The name or abbreviation of the shipping location or region. Countries are returned through ISO 3166 codes . This field may also include continents and other larger geographical regions (for example, the Middle East, Southeast Asia), as well as domestic/special locations (like APO/FPO, PO Box, Alask |
