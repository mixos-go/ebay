---
title: getSalesTax
category: Account_v1_API
api_name: getSalesTax
method: GET
path: /sales_tax/{countryCode}/{jurisdictionId}
---

**Category:** Account_v1_API
**API:** getSalesTax

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/sales_tax/{countryCode}/{jurisdictionId}

## API Description
This call retrieves the current sales-tax table entry for a specific tax jurisdiction. Specify the jurisdiction to retrieve using the countryCode and jurisdictionId path parameters. All four response fields will be returned if a sales-tax entry exists for the tax jurisdiction. Otherwise, the response will be returned as empty. Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces. Important! In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table. However, sellers may continue to use a sales-tax table to set rates for the following US territories: American Samoa (AS) Guam (GU) Northern Mariana Islands (MP) Palau (PW) US Virgin Islands (VI) For additional information, refer to Taxes and import charges .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| countryCode (path) | string | Yes | This path parameter specifies the two-letter ISO 3166 code for the country whose sales tax table you want to retrieve. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA |
| jurisdictionId (path) | string | Yes | This path parameter specifies the ID of the sales tax jurisdiction for the tax table entry to be retrieved. Valid jurisdiction IDs can be retrieved using the getSalesTaxJurisdiction method of the Metadata API. Note: When countryCode is set to US , the only supported values for jurisdictionId are: AS |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| countryCode | string | No | The country code enumeration value identifies the country to which this sales tax rate applies. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA For implementation help, refer to eBay API documentation |
| salesTaxJurisdictionId | string | No | A unique ID that identifies the sales tax jurisdiction to which the sales tax rate applies. Note: When the returned countryCode is US , the only supported return values for salesTaxJurisdictionId are: AS (American Samoa) GU (Guam MP Northern Mariana Islands PW (Palau) VI (US Virgin Islands) |
| salesTaxPercentage | string | No | The sales tax rate that will be applied to sales price. The shippingAndHandlingTaxed value will indicate whether or not sales tax is also applied to shipping and handling charges Although it is a string, a percentage value is returned here, such as 7.75 |
| shippingAndHandlingTaxed | boolean | No | If returned as true , sales tax is also applied to shipping and handling charges, and not just the total sales price of the order. |
