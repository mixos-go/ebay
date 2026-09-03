---
title: getPromotionReports
category: Marketing_API
api_name: getPromotionReports
method: GET
path: /promotion_report
---

**Category:** Marketing_API
**API:** getPromotionReports

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/promotion_report

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method generates a report that lists the seller's running, paused, and ended discounts for the specified eBay marketplace. The result set can be filtered by the discount status and the number of results to return. You can also supply keywords to limit the report to discounts that contain the specified keywords. Specify the eBay marketplace for which you want the report run using the marketplace_id query parameter. Supply additional query parameters to control the report as needed.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | Specifies the maximum number of discounts returned on a page from the result set. Default: 200 Maximum: 200 |
| marketplace_id (query) | string | Yes | This parameter specifies the eBay marketplace ID of the site for which you want the discounts report. See MarketplaceIdEnum for supported Marketplace ID values. |
| offset (query) | string | No | Specifies the number of discounts to skip in the result set before returning the first discount in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the  |
| promotion_status (query) | string | No | This parameter specifies the discount state by which you want to filter the results. See PromotionStatusEnum for supported values. Maximum number of input values: 1 |
| promotion_type (query) | string | No | This parameter specifies the campaign discount type by which you want to filter the results. See PromotionTypeEnum for supported values. |
| q (query) | string | No | A string consisting of one or more keywords . eBay filters the response by returning only the discounts that contain the supplied keywords in the discount title. Example: "iPhone" or "Harry Potter." Commas that separate keywords are ignored. For example, a keyword string of "iPhone, iPad" equals "iP |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length : 2048 |
| promotionReports | array<PromotionReportDetail> | No | A list of promotionReports contained in the paginated result set. |
| promotionReports.averageItemDiscount | Amount | No | The average item discount is the average discount that has been applied to each item being discounted. This value is calculated as follows: totalDiscount / itemsSoldQuantity = averageItemDiscount |
| promotionReports.averageItemDiscount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.averageItemDiscount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.averageItemRevenue | Amount | No | The average item revenue is the average revenue that has been received for each item being discounted.. This value is calculated as follows: totalSales / itemsSoldQuantity = averageItemRevenue |
| promotionReports.averageItemRevenue.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.averageItemRevenue.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.averageOrderDiscount | Amount | No | The average order discount is the average discount that has been applied to each order that has an active discount. This value is calculated as follows: totalDiscount / numberOfOrdersSold = averageOrderDiscount |
| promotionReports.averageOrderDiscount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.averageOrderDiscount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.averageOrderRevenue | Amount | No | The average order revenue is the average revenue that has been received for each order that has an active discount. This value is calculated as follows: totalSales / numberOfOrdersSold = averageOrderRevenue |
| promotionReports.averageOrderRevenue.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.averageOrderRevenue.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.averageOrderSize | string | No | The average order size is the average number of items that each order contained that have an active discount. This value is calculated as follows: itemsSoldQuantity / numberOfOrdersSold = averageOrderSize |
| promotionReports.baseSale | Amount | No | This is the monetary amount of items purchased that have been discounted where the threshold wasn't met , so the discount was not applied. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. One buyer purchased only one pair of socks, so they pay the full price of $5. H |
| promotionReports.baseSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.baseSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.itemsSoldQuantity | integer | No | This is the quantity of items purchased in a threshold discount where the threshold has been met and the discount was applied. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. One buyer purchases two pairs of socks, so they pay $7.50 for both pairs (rather than the f |
| promotionReports.numberOfOrdersSold | integer | No | This is the number of orders sold in a threshold discount where the threshold has been met and the discount was applied. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. One buyer purchases two pairs of socks, so they pay $7.50 for both pairs (rather than the full pr |
| promotionReports.percentageSalesLift | string | No | The percentage sales lift is the total dollar amount gained due to discounts. This value is calculated as follows: promotionSale / totalSale = percentageSalesLift |
| promotionReports.promotionHref | string | No | The URI of the discount report. |
| promotionReports.promotionId | string | No | A unique eBay-assigned ID for the discount that's generated when the discount is created. |
| promotionReports.promotionReportId | string | No | The unique eBay-assigned ID of the discount report that is generated when the report is created. |
| promotionReports.promotionSale | Amount | No | This is the monetary amount of the items sold in a threshold discount where the threshold has been met and the discount was applied. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. One buyer purchases two pairs of socks, so they pay $7.50 for both pairs (rather than |
| promotionReports.promotionSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.promotionSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.promotionType | string | No | Indicates the type of the discount, either CODED_COUPON , MARKDOWN_SALE , ORDER_DISCOUNT , or VOLUME_DISCOUNT . For implementation help, refer to eBay API documentation |
| promotionReports.totalDiscount | Amount | No | This is the monetary discount amount applied to the sale of items in a threshold discount where the threshold has been met and the discount was applied. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. One buyer purchases two pairs of socks, so they pay $7.50 for bot |
| promotionReports.totalDiscount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.totalDiscount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| promotionReports.totalSale | Amount | No | This is the total monetary sales amount of all items sold that were discounted. For example, suppose you're running a "Buy 1, get 1 at 50%" discount on $5 socks. You make one sale where the buyer purchases only one pair of socks and they pay the full price of $5 ( baseSale ). You make a second sale  |
| promotionReports.totalSale.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| promotionReports.totalSale.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0 . |
