---
title: getSalesTaxes
category: Account_v1_API
api_name: getSalesTaxes
method: GET
path: /sales_tax
---

**Category:** Account_v1_API
**API:** getSalesTaxes

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/sales_tax

## API Description
Use this call to retrieve all sales tax table entries that the seller has defined for a specific country. All four response fields will be returned for each tax jurisdiction that matches the search criteria. If no sales tax rates are defined for the specified, a 204 No Content status code is returned with no response payload. Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces. Important! In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table. However, sellers may continue to use a sales-tax table to set rates for the following US territories: American Samoa (AS) Guam (GU) Northern Mariana Islands (MP) Palau (PW) US Virgin Islands (VI) For additional information, refer to Taxes and import charges .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| country_code (query) | string | Yes | This path parameter specifies the two-letter ISO 3166 code for the country whose tax table you want to retrieve. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA For implementation help, refer to eBay API documentation at h |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| salesTaxes | array<SalesTax> | No | An array of one or more sales-tax rate entries for a specified country. If no sales-tax rate entries are set up, no response payload is returned, but an HTTP status code of 204 No Content is returned. |
| salesTaxes.countryCode | string | No | The country code enumeration value identifies the country to which this sales tax rate applies. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA For implementation help, refer to eBay API documentation |
| salesTaxes.salesTaxJurisdictionId | string | No | A unique ID that identifies the sales tax jurisdiction to which the sales tax rate applies. Note: When the returned countryCode is US , the only supported return values for salesTaxJurisdictionId are: AS (American Samoa) GU (Guam MP Northern Mariana Islands PW (Palau) VI (US Virgin Islands) |
| salesTaxes.salesTaxPercentage | string | No | The sales tax rate that will be applied to sales price. The shippingAndHandlingTaxed value will indicate whether or not sales tax is also applied to shipping and handling charges Although it is a string, a percentage value is returned here, such as 7.75 |
| salesTaxes.shippingAndHandlingTaxed | boolean | No | If returned as true , sales tax is also applied to shipping and handling charges, and not just the total sales price of the order. |
