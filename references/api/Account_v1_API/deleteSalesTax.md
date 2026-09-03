---
title: deleteSalesTax
category: Account_v1_API
api_name: deleteSalesTax
method: DELETE
path: /sales_tax/{countryCode}/{jurisdictionId}
---

**Category:** Account_v1_API
**API:** deleteSalesTax

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/sales_tax/{countryCode}/{jurisdictionId}

## API Description
This call deletes a sales-tax table entry for a jurisdiction. Specify the jurisdiction to delete using the countryCode and jurisdictionId path parameters. Note: Sales-tax tables are only available for the US (EBAY_US) and Canada (EBAY_CA) marketplaces.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| countryCode (path) | string | Yes | This path parameter specifies the two-letter ISO 3166 code for the country whose sales tax table entry you want to delete. Note: Sales-tax tables are available only for the US and Canada marketplaces. Therefore, the only supported values are: US CA |
| jurisdictionId (path) | string | Yes | This path parameter specifies the ID of the sales tax jurisdiction whose table entry you want to delete. Valid jurisdiction IDs can be retrieved using the getSalesTaxJurisdiction method of the Metadata API. Note: When countryCode is set to US , the only supported values for jurisdictionId are: AS (A |

## Response
_No documented response fields._
