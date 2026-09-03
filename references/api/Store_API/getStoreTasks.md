---
title: getStoreTasks
category: Store_API
api_name: getStoreTasks
method: GET
path: /store/tasks
---

**Category:** Store_API
**API:** getStoreTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/store/tasks

## API Description
This method retrieves the status of all async store tasks for a store. Every task is set as FAILED or COMPLETED once it's execution time reaches 24 hours.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task | array<StoreTaskType> | No | This array provides detailed information about the status of one or more store tasks. |
| task.id | string | No | The unique identifier of an eBay Store task. |
| task.message | string | No | This field provides a textual description on the status of the task, and could help user troubleshoot any issues if there is an issue with eBay creating the task. |
| task.status | string | No | The enumeration value here indicates the processing status of the task. See the StoreTaskStatusEnum type for more information on supported status values. For implementation help, refer to eBay API documentation |
| task.type | string | No | The enumeration value indicates the task type. For implementation help, refer to eBay API documentation |
