---
title: getCurrencies
category: Metadata_API
api_name: getCurrencies
method: GET
path: /marketplace/{marketplace_id}/get_currencies
---

**Category:** Metadata_API
**API:** getCurrencies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_currencies

## API Description
This method returns the default currency used by the eBay marketplace specified in the request. This is the currency that the seller should use when providing price data for this marketplace through listing APIs.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which currency information is retrieved. See the MarketplaceIdEnum type for a list of supported eBay marketplace ID values. |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada and French Belgium marketplaces. Follow the instructions below to retrieve metadata for these marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Language header with a value |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| defaultCurrency | Currency | No | This field specifies the default currency used by the marketplace. |
| defaultCurrency.code | string | No | The three-letter ISO 4217 code returned. Restriction: Only the currency of the marketplace is supported. Examples: on the US marketplace, the only currency supported is the United States dollar, USD ; on the Canadian marketplace, the only currency supported is the Canadian dollar, CAD . For implemen |
| defaultCurrency.description | string | No | The description of the returned three-letter code. For example, if the code is USD , the description returned would be US Dollar . |
| marketplaceId | string | No | The ID of the eBay marketplace to which the default currency applies. For implementation help, refer to eBay API documentation |
