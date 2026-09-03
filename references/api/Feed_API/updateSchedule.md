---
title: updateSchedule
category: Feed_API
api_name: updateSchedule
method: PUT
path: /schedule/{schedule_id}
---

**Category:** Feed_API
**API:** updateSchedule

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/schedule/{schedule_id}

## API Description
This method updates an existing schedule. Specify the schedule to update using the schedule_id path parameter. If the schedule template has changed after the schedule was created or updated, the input will be validated using the changed template. Note: Make sure to include all fields required by the schedule template ( scheduleTemplateId ). Call the getScheduleTemplate method (or the getScheduleTemplates method), to find out which fields are required or optional. If you do not know the scheduleTemplateId , call the getSchedule method to find out.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| schedule_id (path) | string | Yes | This path parameter is the unique identifier of the schedule being updated. Use the getSchedules method to retrieve schedule IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| preferredTriggerDayOfMonth | integer | No | The preferred day of the month to trigger the schedule. This field can be used with preferredTriggerHour for monthly schedules. The last day of the month is used for numbers larger than the actual number of days in the month. This field is available as specified by the template ( scheduleTemplateId  |
| preferredTriggerDayOfWeek | string | No | The preferred day of the week to trigger the schedule. This field can be used with preferredTriggerHour for weekly schedules. This field is available as specified by the template ( scheduleTemplateId ). The template can specify this field as optional or required, and optionally provides a default va |
| preferredTriggerHour | string | No | The preferred two-digit hour of the day to trigger the schedule. This field is available as specified by the template ( scheduleTemplateId ). The template can specify this field as optional or required, and optionally provides a default value. Format: UTC hhZ For example, the following represents 11 |
| scheduleEndDate | string | No | The timestamp on which the schedule (report generation) ends. After this date, the schedule status becomes INACTIVE . Use this field, if available, to end the schedule in the future. This value must be later than scheduleStartDate (if supplied). This field is available as specified by the template ( |
| scheduleName | string | No | The schedule name assigned by the user for the created schedule. |
| scheduleStartDate | string | No | The timestamp to start generating the report. After this timestamp, the schedule status becomes active until either the scheduleEndDate occurs or the scheduleTemplateId becomes inactive. Use this field, if available, to start the schedule in the future but before the scheduleEndDate (if supplied). T |
| schemaVersion | string | No | The schema version of a schedule. |

## Response
_No documented response fields._
