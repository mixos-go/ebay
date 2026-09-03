---
title: getReport
category: Marketing_API
api_name: getReport
method: GET
path: /ad_report/{report_id}
---

**Category:** Marketing_API
**API:** getReport

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_report/{report_id}

## API Description
This call downloads the report as specified by the report_id path parameter. Call createReportTask to schedule and generate a Promoted Listings report. All date values are returned in UTC format ( yyyy-MM-ddThh:mm:ss.sssZ ). Note: The reporting of some data related to sales and ad-fees may require a 72-hour ( maximum ) adjustment period which is often referred to as the Reconciliation Period . Such adjustment periods should, on average, be minimal. However, at any given time, the payments tab may be used to view those amounts that have actually been charged. Important! For ad_report and ad_report_task methods, the API call limit is subject to a per user quota. These API calls can only be executed a maximum of 200 times per hour for each seller/user. If the number of calls per hour exceeds this limit, any new calls will be blocked for the next hour.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| report_id (path) | string | Yes | This path parameter specifies the unique ID of the Promoted Listings report being retrieved. Use the getReportTasks method to retrieve report IDs. |

## Response
_No documented response fields._
