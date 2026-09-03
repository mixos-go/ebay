---
title: getInventoryTask
category: Feed_API
api_name: getInventoryTask
method: GET
path: /inventory_task/{task_id}
---

**Category:** Feed_API
**API:** getInventoryTask

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/inventory_task/{task_id}

## API Description
This method retrieves the task details and status of the specified inventory-related task. The input is task_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the inventory task being retrieved. Use the getInventoryTasks method to retrieve inventory task IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| taskId | string | No | The ID of the task. This ID is generated when the task was created by the createInventoryTask method. |
| status | string | No | The status of the task. Users must wait until status is complete before moving on to the next step (such as uploading/downloading a file). For implementation help, refer to eBay API documentation |
| feedType | string | No | The feed type associated with the inventory task. |
| creationDate | string | No | The date the task was created. |
| completionDate | string | No | The timestamp when the task status went into the COMPLETED , COMPLETED_WITH_ERROR , or PARTIALLY_PROCESSED state. This field is only returned if the status is one of the three completed values. |
| schemaVersion | string | No | The schema version number associated with the task. |
| detailHref | string | No | The path to the call URI used to retrieve the task. This field points to the getInventoryTask URI. |
| uploadSummary | UploadSummary | No | This container provides summary information on an upload feed (not applicable for download feed types). |
| uploadSummary.failureCount | integer | No | The number of records, such as the number of listings created or the number of pictures uploaded to a listing, that failed to process during the upload feed. Check the response file and correct any issues mentioned. If the feed fails before processing, no response file is provided. In this case chec |
| uploadSummary.successCount | integer | No | The number of records that were successfully processed during the upload feed. |
| filterCriteria | InventoryFilterCriteria | No | This container is used to set the filter criteria for the ActiveInventoryReport. A seller can retrieve listings for a specified format. |
| filterCriteria.listingFormat | string | No | The listing format for the ActiveInventoryReport being created. Supported types are: AUCTION FIXED_PRICE For implementation help, refer to eBay API documentation |
