---
title: getExcludeShippingLocations
category: Metadata_API
api_name: getExcludeShippingLocations
method: GET
path: /shipping/marketplace/{marketplace_id}/get_exclude_shipping_locations
---

**Category:** Metadata_API
**API:** getExcludeShippingLocations

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping/marketplace/{marketplace_id}/get_exclude_shipping_locations

## API Description
This method retrieves a list of locations that the seller can use as excluded shipping locations within their listings or in their fulfillment business policies for the specified marketplace. These are locations that a seller designates as areas where they will not ship items. Excluded shipping locations and ship-to locations are used in tandem at the listing level and in fulfillment business policies. Excluded shipping locations and ship-to locations share a lot of the same values and they should not contradict each other. Manage excluded shipping locations using business policies through the fulfillment_policy resource of the Account v1 API .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which excluded shipping locations information is retrieved. See MarketplaceIdEnum for supported eBay marketplace ID values. Note: When listing the items on the French Canada, French Belgium, and Dutch Belgium marketplaces, also set the Accept-La |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| excludeShippingLocations | array<ShippingExcludeLocation> | No | The complete list of geographical regions, countries, domestic areas, and special locations for the specified eBay marketplace that the seller has designated as excluded shipping locations. |
| excludeShippingLocations.description | string | No | The localized location name. |
| excludeShippingLocations.location | string | No | The location or region to be excluded. Countries are returned through ISO 3166 codes . This field may also include continents and other larger geographical regions (for example, the Middle East, Southeast Asia), as well as domestic/special locations (like APO/FPO, PO Box, Alaska/Hawaii). The values  |
| excludeShippingLocations.region | string | No | The region of the excluded shipping area specified, such as: Africa Americas Asia Central America and Caribbean Europe Middle East North America Oceania South America Southeast Asia |
