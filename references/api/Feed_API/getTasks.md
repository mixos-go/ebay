---
title: getTasks
category: Feed_API
api_name: getTasks
method: GET
path: /task
---

**Category:** Feed_API
**API:** getTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/task

## API Description
This method returns the details and status for an array of tasks based on a specified feed_type or schedule_id . Specifying both feed_type and schedule_id results in an error. Since schedules are based on feed types, you can specify a schedule ( schedule_id ) that returns the needed feed_type . If specifying the feed_type , limit which tasks are returned by specifying filters, such as the creation date range or period of time using look_back_days . Also, by specifying the feed_type , both on-demand and scheduled reports are returned. If specifying a schedule_id , the schedule template (that the schedule ID is based on) determines which tasks are returned (see schedule_id for additional information). Each scheduledId applies to one feed_type .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| date_range (query) | string | No | Specifies the range of task creation dates used to filter the results. The results are filtered to include only tasks with a creation date that is equal to this date or is within specified range. Only tasks that are less than 90 days can be retrieved. Note: Maximum date range window size is 90 days. |
| feed_type (query) | string | No | The feed type associated with the tasks to be returned. Only use a feedType that is available for your API: Order Feeds: LMS_ORDER_ACK, LMS_ORDER_REPORT Inventory Upload Feed Types: See Available FeedTypes Do not use with the schedule_id parameter. Since schedules are based on feed types, you can sp |
| limit (query) | string | No | The maximum number of tasks that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. Note: This feature employs a zero-based list, where the first item in the list has an offset of 0 . For exampl |
| look_back_days (query) | string | No | The number of previous days in which to search for tasks. Do not use with the date_range parameter. If both date_range and look_back_days are omitted, this parameter's default value is used. Default: 7 Range: 1-90 (inclusive) |
| offset (query) | string | No | The number of tasks to skip in the result set before returning the first task in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the response contains  |
| schedule_id (query) | string | No | The unique identifier associated with the tasks being returned. A schedule periodically generates a report for the feed type specified by the schedule template. Note: Schedules are currently only available for LMS_ORDER_REPORT . Do not use with the feed_type parameter. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of tasks to return per page, from the result set. A result set is the complete set of tasks returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter default |
| next | string | No | The path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The path to the call URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| tasks | array<Task> | No | An array of the tasks on this page. The tasks are sorted by creation date. An empty array is returned if the filter criteria excludes all tasks. |
| tasks.completionDate | string | No | The timestamp when the task went into the COMPLETED or COMPLETED_WITH_ERROR state. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the seller can run a getResultFile call to download the report. |
| tasks.creationDate | string | No | The date the task was created. |
| tasks.detailHref | string | No | The path to the call URI used to retrieve the task. This field points to the GetOrderTask URI if the task is for LMS_ORDER_REPORT or will be null if this task is for LMS_ORDER_ACK . |
| tasks.feedType | string | No | The feed type associated with the task. |
| tasks.schemaVersion | string | No | The schema version number associated with the task. |
| tasks.status | string | No | The enumeration value that indicates the state of the task that was submitted in the request. See FeedStatusEnum for information. The values COMPLETED and COMPLETED_WITH_ERROR indicate the Order Report file is ready to download. For implementation help, refer to eBay API documentation |
| tasks.taskId | string | No | The ID of the task that was submitted in the request. |
| tasks.uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| tasks.uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| tasks.uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
| total | integer | No | The total number of tasks that match the input criteria. |
