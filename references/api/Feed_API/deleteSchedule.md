---
title: deleteSchedule
category: Feed_API
api_name: deleteSchedule
method: DELETE
path: /schedule/{schedule_id}
---

**Category:** Feed_API
**API:** deleteSchedule

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/schedule/{schedule_id}

## API Description
This method deletes an existing schedule. Specify the schedule to delete using the schedule_id path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| schedule_id (path) | string | Yes | This path parameter is the unique identifier of the schedule being deleted. Use the getSchedules method to retrieve schedule IDs. |

## Response
_No documented response fields._
