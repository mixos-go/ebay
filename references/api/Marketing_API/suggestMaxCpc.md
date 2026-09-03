---
title: suggestMaxCpc
category: Marketing_API
api_name: suggestMaxCpc
method: POST
path: /ad_campaign/suggest_max_cpc
---

**Category:** Marketing_API
**API:** suggestMaxCpc

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/suggest_max_cpc

## API Description
Note: This method is only supported for smart targeting priority strategy campaigns. Sellers can use the getAdvertisingEligibility method of the Account API v1 to determine if they are eligible for a priority strategy campaign. This method allows sellers to retrieve the suggested maximum cost-per-click value for a smart targeting campaign. This value is required when creating a smart targeting campaign and indicates the maximum amount for which the eBay suggested bid can be adjusted.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingIds | array<string> | No | A comma delimited array of listing Ids the seller plans to associate with the smart targeting campaign for which the maxCpc will be suggested. |
| marketplaceId | string | No | The unique identifier of the marketplace where the listings are hosted. See MarketplaceIdEnum for supported values. For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| amount | Amount | No | The suggested maxCpc amount for the smart targeting campaign. |
| amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| marketplaceId | string | No | The unique identifier of the marketplace where the listings are hosted. For implementation help, refer to eBay API documentation |
