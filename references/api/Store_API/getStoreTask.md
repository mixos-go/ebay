---
title: getStoreTask
category: Store_API
api_name: getStoreTask
method: GET
path: /store/tasks/{task_id}
---

**Category:** Store_API
**API:** getStoreTask

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/store/tasks/{task_id}

## API Description
This method retrieves the current status of a recent store operation. The unique identifier of the task is passed in as a path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | The unique identifier of an eBay Store async task. A taskId value is returned in the response of other successful calls. (e.g.addStoreCategory, moveStoreCategory, deleteStoreCategory). |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task | StoreTaskType | No | This container provides detailed information about the status of the store task. |
| task.id | string | No | The unique identifier of an eBay Store task. |
| task.message | string | No | This field provides a textual description on the status of the task, and could help user troubleshoot any issues if there is an issue with eBay creating the task. |
| task.status | string | No | The enumeration value here indicates the processing status of the task. See the StoreTaskStatusEnum type for more information on supported status values. For implementation help, refer to eBay API documentation |
| task.type | string | No | The enumeration value indicates the task type. For implementation help, refer to eBay API documentation |
