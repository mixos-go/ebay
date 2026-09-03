---
title: getSchedule
category: Feed_API
api_name: getSchedule
method: GET
path: /schedule/{schedule_id}
---

**Category:** Feed_API
**API:** getSchedule

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/schedule/{schedule_id}

## API Description
This method retrieves schedule details and status of the specified schedule. Specify the schedule to retrieve using the schedule_id . Use the getSchedules method to find a schedule if you do not know the schedule_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| schedule_id (path) | string | Yes | This path parameter is the unique identifier of the schedule for which to retrieve details. Use the getSchedules method to retrieve schedule IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| scheduleId | string | No | The ID of the schedule. This ID is generated when the schedule was created by the createSchedule method. |
| creationDate | string | No | The creation date of the schedule in hours based on the 24-hour Coordinated Universal Time (UTC) clock. |
| feedType | string | No | The feedType associated with the schedule. |
| lastModifiedDate | string | No | The date the schedule was last modified. |
| preferredTriggerDayOfMonth | integer | No | The preferred day of the month to trigger the schedule. This field can be used with preferredTriggerHour for monthly schedules. The last day of the month is used for numbers larger than the number of days in the month. |
| preferredTriggerDayOfWeek | string | No | The preferred day of the week to trigger the schedule. This field can be used with preferredTriggerHour for weekly schedules. For implementation help, refer to eBay API documentation |
| preferredTriggerHour | string | No | The preferred two-digit hour of the day to trigger the schedule. Format: UTC hhZ For example, the following represents 11:00 am UTC: 11Z |
| scheduleEndDate | string | No | The timestamp on which the report generation (subscription) ends. After this date, the schedule status becomes INACTIVE . |
| scheduleName | string | No | The schedule name assigned by the user for the created schedule. Users assign this name for their reference. |
| scheduleStartDate | string | No | The timestamp that indicates the start of the report generation. |
| scheduleTemplateId | string | No | The ID of the template used to create this schedule. |
| schemaVersion | string | No | The schema version of the feedType for the schedule. |
| status | string | No | The enumeration value that indicates the state of the schedule. For implementation help, refer to eBay API documentation |
| statusReason | string | No | The reason the schedule is inactive. For implementation help, refer to eBay API documentation |
