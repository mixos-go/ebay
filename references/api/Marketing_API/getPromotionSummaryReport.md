---
title: getPromotionSummaryReport
category: Marketing_API
api_name: getPromotionSummaryReport
method: GET
path: /promotion_summary_report
---

**Category:** Marketing_API
**API:** getPromotionSummaryReport

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/promotion_summary_report

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method generates a report that summarizes the seller's discounts for the specified eBay marketplace. The report returns information on RUNNING , PAUSED , and ENDED discounts (deleted reports are not returned) and summarizes the seller's campaign performance for all discounts on a given site. For information about summary reports, see Reading the item discount Summary report .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (query) | string | Yes | This parameter specifies the eBay marketplace ID of the site for which you want a discount summary report. See MarketplaceIdEnum for supported Marketplace ID values. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| baseSale | Amount | No | The total revenue from all the purchased items that were part of a discount but did not trigger a discount during the discount period. |
| baseSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| baseSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| lastUpdated | string | No | The date the report was generated. |
| percentageSalesLift | string | No | The percentage of the total dollar amount gained due to discounts. This value is calculated as follows: precentageSalesLift = promotionSale / ( baseSale + promotionSale ) |
| promotionSale | Amount | No | The total revenue from all the purchased items that were part of a discount and their purchase did trigger a discount during the discount period. |
| promotionSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| totalSale | Amount | No | Total dollar sales amount of all the seller's listings, current to the date the report was generated. |
| totalSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| totalSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
