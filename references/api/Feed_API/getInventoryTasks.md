---
title: getInventoryTasks
category: Feed_API
api_name: getInventoryTasks
method: GET
path: /inventory_task
---

**Category:** Feed_API
**API:** getInventoryTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/inventory_task

## API Description
This method searches for multiple tasks of a specific feed type, and includes date filters and pagination.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feed_type (query) | string | No | The feed type associated with the inventory tasks being retrieved. Presently, only one feed type is available: LMS_ACTIVE_INVENTORY_REPORT See Report value feed types for more information. |
| schedule_id (query) | string | No | Note: Schedule functionality for ActiveInventoryReport is currently unavailable, so this field is not usable. |
| look_back_days (query) | string | No | The number of previous days in which to search for tasks. Do not use with the date_range parameter. If both date_range and look_back_days are omitted, this parameter's default value is used. Default: 7 Range: 1-90 (inclusive) |
| date_range (query) | string | No | Specifies the range of task creation dates used to filter the results. The results are filtered to include only tasks with a creation date that is equal to this date or is within specified range. Note: Maximum date range window size is 90 days. Valid Format (UTC): yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-d |
| limit (query) | string | No | The maximum number of tasks that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. Note: This feature employs a zero-based list, where the first item in the list has an offset of 0 . For exampl |
| offset (query) | string | No | The number of tasks to skip in the result set before returning the first task in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the response contains  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of inventory tasks to return per page, from the result set. A result set is the complete set of tasks returned by the method. Note: Though this parameter is not required to be submitted in the request, the paramet |
| next | string | No | The path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be specified in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list, where the first item in the list has an offset of 0 . |
| prev | string | No | The path to the call URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| tasks | array<InventoryTask> | No | An array of the inventory tasks on this page. The tasks are sorted by creation date. Note: An empty array is returned if the filter criteria excludes all tasks. |
| tasks.taskId | string | No | The ID of the task. This ID is generated when the task was created by the createInventoryTask method. |
| tasks.status | string | No | The status of the task. Users must wait until status is complete before moving on to the next step (such as uploading/downloading a file). For implementation help, refer to eBay API documentation |
| tasks.feedType | string | No | The feed type associated with the inventory task. |
| tasks.creationDate | string | No | The date the task was created. |
| tasks.completionDate | string | No | The timestamp when the task status went into the COMPLETED , COMPLETED_WITH_ERROR , or PARTIALLY_PROCESSED state. This field is only returned if the status is one of the three completed values. |
| tasks.schemaVersion | string | No | The schema version number associated with the task. |
| tasks.detailHref | string | No | The path to the call URI used to retrieve the task. This field points to the getInventoryTask URI. |
| tasks.uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| tasks.uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| tasks.uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
| tasks.filterCriteria | InventoryFilterCriteria | No | This container is used to set the filter criteria for the ActiveInventoryReport. A seller can retrieve listings for a specified format. |
| tasks.filterCriteria.listingFormat | string | No | The listing format for the ActiveInventoryReport being created. Supported types are: AUCTION FIXED_PRICE For implementation help, refer to eBay API documentation |
| total | integer | No | The total number of inventory tasks that match the input criteria. |
