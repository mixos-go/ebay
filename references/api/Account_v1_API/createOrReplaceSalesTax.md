---
title: createOrReplaceSalesTax
category: Account_v1_API
api_name: createOrReplaceSalesTax
method: PUT
path: /sales_tax/{countryCode}/{jurisdictionId}
---

**Category:** Account_v1_API
**API:** createOrReplaceSalesTax

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/sales_tax/{countryCode}/{jurisdictionId}

## API Description
This method creates or updates a sales-tax table entry for a jurisdiction. Specify the tax table entry you want to configure using the two path parameters: countryCode and jurisdictionId . A tax table entry for a jurisdiction is comprised of two fields: one for the jurisdiction's sales-tax rate and another that's a boolean value indicating whether or not shipping and handling are taxed in the jurisdiction. You can set up sales-tax tables for countries that support different tax jurisdictions . Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces. Retrieve valid jurisdiction IDs using getSalesTaxJurisdictions in the Metadata API. For details about using this call, refer to Establishing sales-tax tables . Important! In the US, eBay now calculates, collects, and remits sales tax to the proper taxing authorities in all 50 states and Washington, DC. Sellers can no longer specify sales-tax rates for these jurisdictions using a tax table. However, sellers may continue to use a sales-tax table to set rates for the following US territories: American Samoa (AS) Guam (GU) Northern Mariana Islands (MP) Palau (PW) US Virgin Islands (VI) For additional information, refer to Taxes and import charges .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| countryCode (path) | string | Yes | This path parameter specifies the two-letter ISO 3166 code for the country for which you want to create a sales tax table entry. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA |
| jurisdictionId (path) | string | Yes | This path parameter specifies the ID of the tax jurisdiction for the table entry to be created. Valid jurisdiction IDs can be retrieved using the getSalesTaxJurisdiction method of the Metadata API. Note: When countryCode is set to US , the only supported values for jurisdictionId are: AS (American S |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| salesTaxPercentage | string | No | This field is used to set the sales tax rate for the tax jurisdiction set in the call URI. When applicable to an order, this sales tax rate will be applied to sales price. The shippingAndHandlingTaxed value will indicate whether or not sales tax is also applied to shipping and handling charges Altho |
| shippingAndHandlingTaxed | boolean | No | This field is set to true if the seller wishes to apply sales tax to shipping and handling charges, and not just the total sales price of the order. Otherwise, this field's value should be set to false . |

## Response
_No documented response fields._
