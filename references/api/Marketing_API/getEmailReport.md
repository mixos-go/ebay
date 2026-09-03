---
title: getEmailReport
category: Marketing_API
api_name: getEmailReport
method: GET
path: /email_campaign/report
---

**Category:** Marketing_API
**API:** getEmailReport

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/report

## API Description
This method returns the seller's email campaign performance report for a time period specified by the startDate and endDate path parameters. The maximum date range for a report retrieved by this method is one year. Note: The startDate and endDate must be given in UTC format, as shown in the following example: sell/marketing/v1/email_campaign/report?startDate=2022-11-01T19:09:02.768Z&endDate=2022-12-28T19:09:02.768Z The email report returns a list of metrics, such as the number of times an email report has been opened and resulted in clicks.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| endDate (query) | string | Yes | The end date for the report, given in UTC format. The maximum date range for a report retrieved by this method is one year. |
| startDate (query) | string | Yes | The start date for the report, given in UTC format. The maximum date range for a report retrieved by this method is one year. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| clickCount | integer | No | The number of item listing links clicked from the body of campaign emails for the time range specified by the query. |
| openCount | integer | No | The total email opened count for all email campaigns from a seller for the time range specified by the query. |
| totalSales | Amount | No | A seller's total sale amount for the time range specified by the query. |
| totalSales.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| totalSales.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
