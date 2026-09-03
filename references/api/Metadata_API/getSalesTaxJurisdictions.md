---
title: getSalesTaxJurisdictions
category: Metadata_API
api_name: getSalesTaxJurisdictions
method: GET
path: /country/{countryCode}/sales_tax_jurisdiction
---

**Category:** Metadata_API
**API:** getSalesTaxJurisdictions

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/country/{countryCode}/sales_tax_jurisdiction

## API Description
This method retrieves all sales-tax jurisdictions for the country specified in the countryCode path parameter. Countries with valid sales-tax jurisdictions are Canada and the US. The response from this call tells you the jurisdictions for which a seller can configure tax tables. Although setting up tax tables is optional, you can use the createOrReplaceSalesTax method in the Account API call to configure the tax tables for the jurisdictions into which you sell. Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces. Important! In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table. However, sellers may continue to use a sales-tax table to set rates for the following US territories: American Samoa (AS) Guam (GU) Northern Mariana Islands (MP) Palau (PW) US Virgin Islands (VI) For additional information, refer to Taxes and import charges .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| countryCode (path) | string | Yes | This path parameter specifies the two-letter ISO 3166 country code for the country whose jurisdictions you want to retrieve. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| salesTaxJurisdictions | array<SalesTaxJurisdiction> | No | A list of sales-tax jurisdictions. |
| salesTaxJurisdictions.salesTaxJurisdictionId | string | No | The unique ID for a sales-tax jurisdiction. Important! When countryCode is set to US , IDs for all 50 states, Washington, DC, and all US territories will be returned. However, the only salesTaxJurisdictionId values currently supported are: AS (American Samoa) GU (Guam MP Northern Mariana Islands PW  |
