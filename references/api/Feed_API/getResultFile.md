---
title: getResultFile
category: Feed_API
api_name: getResultFile
method: GET
path: /task/{task_id}/download_result_file
---

**Category:** Feed_API
**API:** getResultFile

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/task/{task_id}/download_result_file

## API Description
This method retrieves the generated file that is associated with the specified task ID. The response of this call is a compressed or uncompressed CSV, XML, or JSON file, with the applicable file extension (for example: csv.gz). For details about how this method is used, see Working with Order Feeds in the Selling Integration Guide. Note: The status of the task to retrieve must be in the COMPLETED or COMPLETED_WITH_ERROR state before this method can retrieve the file. You can use the getTask or getTasks method to retrieve the status of the task.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the task associated with the file to be downloaded. Use the getTasks method to retrieve task IDs. |

## Response
_No documented response fields._
