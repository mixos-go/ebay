---
title: createOrderTask
category: Feed_API
api_name: createOrderTask
method: POST
path: /order_task
---

**Category:** Feed_API
**API:** createOrderTask

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/order_task

## API Description
This method creates an order download task with filter criteria for the order report. When using this method, specify the feedType , schemaVersion , and filterCriteria for the report. The method returns the location response header containing the getOrderTask call URI to retrieve the order task you just created. The URL includes the eBay-assigned task ID, which you can use to reference the order task. To retrieve the status of the task, use the getOrderTask method to retrieve a single task ID or the getOrderTasks method to retrieve multiple order task IDs. Note: The scope depends on the feed type. An error message results when an unsupported scope or feed type is specified. The following list contains this method's authorization scope and its corresponding feed type: https://api.ebay.com/oauth/api_scope/sell.fulfillment: LMS_ORDER_REPORT For details about how this method is used, see General feed types in the Selling Integration Guide. Note: At this time, the createOrderTask method only supports order creation date filters and not modified order date filters. Do not include the modifiedDateRange filter in your request payload.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The feed type associated with the task. The only presently supported value is LMS_ORDER_REPORT . See Report download feed types for more information. |
| filterCriteria | OrderFilterCriteria | No | The container for the filter fields. This container is used to set the filter criteria for the order report. A seller can set date range filters and/or can retrieve orders in a specific state. |
| filterCriteria.creationDateRange | DateRange | No | The creation date range of the orders you want returned. Set the date range so it contains less than 10 days (maximum). If you do not specify a DateRange , results from the last 10 days will be returned by default. |
| filterCriteria.creationDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| filterCriteria.creationDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| filterCriteria.modifiedDateRange | DateRange | No | The modified date range of the orders you want returned. Note: This container is for future use. At this time, the createOrderTask method only supports order creation date filters and not modified order date filters. |
| filterCriteria.modifiedDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| filterCriteria.modifiedDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| filterCriteria.orderStatus | string | No | The order status of the orders returned. If the filter is omitted from createOrderTask call, orders that are in both ACTIVE and COMPLETED states are returned. For implementation help, refer to eBay API documentation |
| schemaVersion | string | No | The schema version of the LMS OrderReport. For the LMS_ORDER_REPORT feed type, see the OrderReport reference page to see the present schema version. The schemaVersion value is the version number shown at the top of the OrderReport page. Restriction: This value must be 1113 or higher. The OrderReport |

## Response
_No documented response fields._
