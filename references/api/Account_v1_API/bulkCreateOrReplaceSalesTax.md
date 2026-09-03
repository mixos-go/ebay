---
title: bulkCreateOrReplaceSalesTax
category: Account_v1_API
api_name: bulkCreateOrReplaceSalesTax
method: POST
path: /bulk_create_or_replace_sales_tax
---

**Category:** Account_v1_API
**API:** bulkCreateOrReplaceSalesTax

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_create_or_replace_sales_tax

## API Description
This method creates or updates multiple sales-tax table entries. Sales-tax tables can be set up for countries that support different tax jurisdictions . Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces. Each sales-tax table entry comprises the following parameters: countryCode jurisdictionId salesTaxPercentage shippingAndHandlingTaxed Valid jurisdiction IDs are retrieved using getSalesTaxJurisdictions in the Metadata API. For details about using this call, refer to Establishing sales-tax tables . Important! In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table. However, sellers may continue to use a sales-tax table to set rates for the following US territories: American Samoa (AS) Guam (GU) Northern Mariana Islands (MP) Palau (PW) US Virgin Islands (VI) For additional information, refer to Taxes and import charges .

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| salesTaxInputList | array<SalesTaxInput> | No | The array of sales-tax table entries to be created or updated. |
| salesTaxInputList.countryCode | string | No | This parameter specifies the two-letter ISO 3166 code of the country for which a sales-tax table entry is to be created or updated. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA |
| salesTaxInputList.salesTaxJurisdictionId | string | No | This parameter specifies the ID of the tax jurisdiction for which a sales-tax table entry is to be created or updated. Valid jurisdiction IDs can be retrieved using the getSalesTaxJurisdiction method of the Metadata API. Note: When countryCode is set to US , the only supported values for jurisdictio |
| salesTaxInputList.salesTaxPercentage | string | No | This parameter specifies the sales tax rate for the specified salesTaxJurisdictionId . When applicable to an order, this sales tax rate will be applied to the sales price. The shippingAndHandlingTaxed value indicates whether or not sales tax is also applied to shipping and handling charges Although  |
| salesTaxInputList.shippingAndHandlingTaxed | boolean | No | This parameter is set to true if the seller wishes to apply sales tax to shipping and handling charges and not just the total sales price of an order. Otherwise, this parameter's value should be set to false . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| updatedSalesTaxEntries | array<UpdatedSalesTaxEntry> | No | The array of new and updated sales-tax table entries. |
| updatedSalesTaxEntries.countryCode | string | No | The two-letter ISO 3166 code of the country associated with the sales-tax table entry. |
| updatedSalesTaxEntries.jurisdictionId | string | No | The ID of the tax jurisdiction associated with the sales-tax table entry. |
| updatedSalesTaxEntries.statusCode | integer | No | The HTTP status code for the call. Note: The system returns one HTTP status code regardless of the number of sales-tax table entries provided. Therefore, the same HTTP statusCode will be listed for all sales-tax table entries returned in the payload. |
