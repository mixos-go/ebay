---
title: uploadFile
category: Feed_API
api_name: uploadFile
method: POST
path: /task/{task_id}/upload_file
---

**Category:** Feed_API
**API:** uploadFile

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/task/{task_id}/upload_file

## API Description
This method associates the specified file with the specified task ID and uploads the input file. After the file has been uploaded, the processing of the file begins. Reports often take time to generate and it's common for this method to return an HTTP status of 202, which indicates the report is being generated. Use the getTask with the task ID or getTasks to determine the status of a report. The status flow is QUEUED &gt; IN_PROCESS &gt; COMPLETED or COMPLETED_WITH_ERROR . When the status is COMPLETED or COMPLETED_WITH_ERROR , this indicates the file has been processed and the order report can be downloaded. If there are errors, they will be indicated in the report file. For details of how this method is used in the upload flow, see Working with Order Feeds in the Selling Integration Guide. This call does not have a JSON Request payload but uploads the file as form-data. For example: fileName: &quot;AddFixedPriceItem_Macbook.xml&quot; name: &quot;file&quot; type: &quot;form-data&quot; file: @&quot;/C:/Users/.../AddFixedPriceItem_Macbook.7z&quot; See Samples for information. Note: This method applies to all Seller Hub feed types , and to all LMS feed types except LMS_ORDER_REPORT and LMS_ACTIVE_INVENTORY_REPORT . Note: You must use a Content-Type header with its value set to " multipart/form-data ". See Samples for information. Note: For LMS feed types, upload a regular XML file or an XML file in zipped format (both formats are allowed).

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the task associated with the file that will be uploaded. Use the getTasks method to retrieve task IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to multipart/form-data . For more information, refer to HTTP request headers . |

## Response
_No documented response fields._
