---
title: getRateTables
category: Account_v1_API
api_name: getRateTables
method: GET
path: /rate_table
---

**Category:** Account_v1_API
**API:** getRateTables

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/rate_table

## API Description
This method retrieves a seller's shipping rate tables for the country specified in the country_code query parameter. If you call this method without specifying a country code, the call returns all of the seller's shipping rate tables. The method's response includes a rateTableId for each table defined by the seller. This rateTableId value is used in add/revise item call or in create/update fulfillment business policy call to specify the shipping rate table to use for that policy's domestic or international shipping options. This call currently supports getting rate tables related to the following marketplaces: United States, Canada, United Kingdom, Germany, Australia, France, Italy, and Spain. Note: Rate tables created with the Trading API might not have been assigned a rateTableId at the time of their creation. This method can assign and return rateTableId values for rate tables with missing IDs if you make a request using the country_code where the seller has defined rate tables. Sellers can define up to 40 shipping rate tables for their account, which lets them set up different rate tables for each of the marketplaces they sell into. Go to Shipping rate tables in My eBay to create and update rate tables.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| country_code (query) | string | No | This query parameter specifies the two-letter ISO 3166 code of country for which you want shipping rate table information. If you do not specify a country code, the request returns all of the seller's defined shipping rate tables for all eBay marketplaces. For implementation help, refer to eBay API  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rateTables | array<RateTable> | No | An array of all shipping rate tables defined for a marketplace (or all marketplaces if no country_code query parameter is used). This array will be returned as empty if the seller has no defined shipping rate tables for the specified marketplace. |
| rateTables.countryCode | string | No | A two-letter ISO 3166 country code representing the eBay marketplace where the shipping rate table is defined. For implementation help, refer to eBay API documentation |
| rateTables.locality | string | No | This enumeration value returned here indicates whether the shipping rate table is a domestic or international shipping rate table. For implementation help, refer to eBay API documentation |
| rateTables.name | string | No | The seller-defined name for the shipping rate table. |
| rateTables.rateTableId | string | No | A unique eBay-assigned ID for a seller's shipping rate table. These rateTableId values are used to associate shipping rate tables to fulfillment business policies or directly to listings through an add/revise/relist call in the Trading API. |
