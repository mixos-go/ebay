---
title: getInputFile
category: Feed_API
api_name: getInputFile
method: GET
path: /task/{task_id}/download_input_file
---

**Category:** Feed_API
**API:** getInputFile

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/task/{task_id}/download_input_file

## API Description
This method downloads the file previously uploaded using uploadFile . Specify the task_id from the uploadFile call. Note: With respect to LMS, this method applies to all feed types except LMS_ORDER_REPORT and LMS_ACTIVE_INVENTORY_REPORT . See LMS API Feeds in the Selling Integration Guide.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the task associated with the input file to be downloaded. Use the getTasks method to retrieve task IDs. |

## Response
_No documented response fields._
