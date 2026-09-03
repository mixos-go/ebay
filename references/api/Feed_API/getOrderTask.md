---
title: getOrderTask
category: Feed_API
api_name: getOrderTask
method: GET
path: /order_task/{task_id}
---

**Category:** Feed_API
**API:** getOrderTask

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/order_task/{task_id}

## API Description
This method retrieves the task details and status of the specified task. The input is task_id . For details about how this method is used, see Working with Order Feeds in the Selling Integration Guide.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the order task being retrieved. Use the getOrderTasks method to retrieve order task IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| completionDate | string | No | The timestamp when the task went into the COMPLETED or COMPLETED_WITH_ERROR state. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the seller can run a getResultFile call to download the report. |
| creationDate | string | No | The date the task was created. |
| detailHref | string | No | The path to the call URI used to retrieve the task. |
| feedType | string | No | The feed type associated with the task. |
| filterCriteria | OrderFilterCriteria | No | A container that returns the filter criteria used. |
| filterCriteria.creationDateRange | DateRange | No | The creation date range of the orders you want returned. Set the date range so it contains less than 10 days (maximum). If you do not specify a DateRange , results from the last 10 days will be returned by default. |
| filterCriteria.creationDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| filterCriteria.creationDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| filterCriteria.modifiedDateRange | DateRange | No | The modified date range of the orders you want returned. Note: This container is for future use. At this time, the createOrderTask method only supports order creation date filters and not modified order date filters. |
| filterCriteria.modifiedDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| filterCriteria.modifiedDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| filterCriteria.orderStatus | string | No | The order status of the orders returned. If the filter is omitted from createOrderTask call, orders that are in both ACTIVE and COMPLETED states are returned. For implementation help, refer to eBay API documentation |
| schemaVersion | string | No | The schema version number associated with the create task. |
| status | string | No | The enumeration value that indicates the state of the task that was submitted in the request. See FeedStatusEnum for information. The values COMPLETED and COMPLETED_WITH_ERROR indicate the Order Report file is ready to download. For implementation help, refer to eBay API documentation |
| taskId | string | No | The ID of the task that was submitted in the request. |
| uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
