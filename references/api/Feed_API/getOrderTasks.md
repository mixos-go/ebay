---
title: getOrderTasks
category: Feed_API
api_name: getOrderTasks
method: GET
path: /order_task
---

**Category:** Feed_API
**API:** getOrderTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/order_task

## API Description
This method returns the details and status for an array of order tasks based on a specified feed_type or schedule_id . Specifying both feed_type and schedule_id results in an error. Since schedules are based on feed types, you can specify a schedule ( schedule_id ) that returns the needed feed_type . If specifying the feed_type , limit which order tasks are returned by specifying filters such as the creation date range or period of time using look_back_days . If specifying a schedule_id , the schedule template (that the schedule_id is based on) determines which order tasks are returned (see schedule_id for additional information). Each schedule_id applies to one feed_type .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| date_range (query) | string | No | The order tasks creation date range. This range is used to filter the results. The filtered results are filtered to include only tasks with a creation date that is equal to this date or is within specified range. Only orders less than 90 days old can be retrieved. Do not use with the look_back_days  |
| feed_type (query) | string | No | The feed type associated with the order tasks being retrieved. The only presently supported value is LMS_ORDER_REPORT See Report download feed types for more information. Note: Do not use with the schedule_id parameter. Since schedules are based on feed types, you can specify a schedule ( schedule_i |
| limit (query) | string | No | The maximum number of order tasks that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. Note: This feature employs a zero-based list, where the first item in the list has an offset of 0 . For  |
| look_back_days (query) | string | No | The number of previous days in which to search for tasks. Do not use with the date_range parameter. If both date_range and look_back_days are omitted, this parameter's default value is used. Default: 7 Range: 1-90 (inclusive) |
| offset (query) | string | No | The number of order tasks to skip in the result set before returning the first order in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the response co |
| schedule_id (query) | string | No | The schedule ID associated with the order tasks being retrieved. A schedule periodically generates a report, and these schedules can be created with the createSchedule method. Note: Do not use with the feed_type parameter. Since schedules are based on feed types, you can specify a schedule ( schedul |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of order tasks to return per page, from the result set. A result set is the complete set of tasks returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter d |
| next | string | No | The path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The path to the call URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| tasks | array<OrderTask> | No | An array of the order tasks on this page. The tasks are sorted by creation date. An empty array is returned if the filter criteria excludes all tasks. |
| tasks.completionDate | string | No | The timestamp when the task went into the COMPLETED or COMPLETED_WITH_ERROR state. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the seller can run a getResultFile call to download the report. |
| tasks.creationDate | string | No | The date the task was created. |
| tasks.detailHref | string | No | The path to the call URI used to retrieve the task. |
| tasks.feedType | string | No | The feed type associated with the task. |
| tasks.filterCriteria | OrderFilterCriteria | No | A container that returns the filter criteria used. |
| tasks.filterCriteria.creationDateRange | DateRange | No | The creation date range of the orders you want returned. Set the date range so it contains less than 10 days (maximum). If you do not specify a DateRange , results from the last 10 days will be returned by default. |
| tasks.filterCriteria.creationDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| tasks.filterCriteria.creationDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| tasks.filterCriteria.modifiedDateRange | DateRange | No | The modified date range of the orders you want returned. Note: This container is for future use. At this time, the createOrderTask method only supports order creation date filters and not modified order date filters. |
| tasks.filterCriteria.modifiedDateRange.from | string | No | The beginning date in the range. If the parent type is included, both the from and/or the to fields become conditionally required. Format: UTC yyyy-MM-ddThh:mm:ss.SSSZ For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:0 |
| tasks.filterCriteria.modifiedDateRange.to | string | No | The end date for the date range, which is inclusive. If the parent type is included, both the from and/or the to fields become conditionally required. For example: Tasks within a range yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddThh:mm:ss.SSSZ Tasks created on March 31, 2021 2021-03-31T00:00:00.000Z..2021-0 |
| tasks.filterCriteria.orderStatus | string | No | The order status of the orders returned. If the filter is omitted from createOrderTask call, orders that are in both ACTIVE and COMPLETED states are returned. For implementation help, refer to eBay API documentation |
| tasks.schemaVersion | string | No | The schema version number associated with the create task. |
| tasks.status | string | No | The enumeration value that indicates the state of the task that was submitted in the request. See FeedStatusEnum for information. The values COMPLETED and COMPLETED_WITH_ERROR indicate the Order Report file is ready to download. For implementation help, refer to eBay API documentation |
| tasks.taskId | string | No | The ID of the task that was submitted in the request. |
| tasks.uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| tasks.uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| tasks.uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
| total | integer | No | The total number of order tasks that match the input criteria. |
