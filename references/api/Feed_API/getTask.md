---
title: getTask
category: Feed_API
api_name: getTask
method: GET
path: /task/{task_id}
---

**Category:** Feed_API
**API:** getTask

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/task/{task_id}

## API Description
This method retrieves the details and status of the specified task. The input is task_id . For details of how this method is used, see Working with Order Feeds in the Selling Integration Guide.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the task being retrieved. Use the getTasks method to retrieve task IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| completionDate | string | No | The timestamp when the task went into the COMPLETED or COMPLETED_WITH_ERROR state. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the seller can run a getResultFile call to download the report. |
| creationDate | string | No | The date the task was created. |
| detailHref | string | No | The path to the call URI used to retrieve the task. This field points to the GetOrderTask URI if the task is for LMS_ORDER_REPORT or will be null if this task is for LMS_ORDER_ACK . |
| feedType | string | No | The feed type associated with the task. |
| schemaVersion | string | No | The schema version number associated with the task. |
| status | string | No | The enumeration value that indicates the state of the task that was submitted in the request. See FeedStatusEnum for information. The values COMPLETED and COMPLETED_WITH_ERROR indicate the Order Report file is ready to download. For implementation help, refer to eBay API documentation |
| taskId | string | No | The ID of the task that was submitted in the request. |
| uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
