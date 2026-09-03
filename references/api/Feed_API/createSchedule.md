---
title: createSchedule
category: Feed_API
api_name: createSchedule
method: POST
path: /schedule
---

**Category:** Feed_API
**API:** createSchedule

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/schedule

## API Description
This method creates a schedule, which is a subscription to the specified schedule template. A schedule periodically generates a report for the feedType specified by the template. Specify the same feedType as the feedType of the associated schedule template. When creating the schedule, if available from the template, you can specify a preferred trigger hour, day of the week, or day of the month. These and other fields are conditionally available as specified by the template. Note: Make sure to include all fields required by the schedule template ( scheduleTemplateId ). Call the getScheduleTemplate method (or the getScheduleTemplates method), to find out which fields are required or optional. If a field is optional and a default value is provided by the template, the default value will be used if omitted from the payload. A successful call returns the location response header containing the getSchedule call URI to retrieve the schedule you just created. The URL includes the eBay-assigned schedule ID, which you can use to reference the schedule task. To retrieve the details of the create schedule task, use the getSchedule method for a single schedule ID or the getSchedules method to retrieve all schedule details for the specified feed_type . The number of schedules for each feedType is limited. Error code 160031 is returned when you have reached this maximum. Note: Except for schedules with a HALF-HOUR frequency, all schedules will ideally run at the start of each hour ('00' minutes). Actual start time may vary time may vary due to load and other factors.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The name of the feed type for the created schedule. Use the getScheduleTemplates method to retrieve the feed type of a schedule template. Note: Schedules are currently only available for LMS_ORDER_REPORT . |
| preferredTriggerDayOfMonth | integer | No | The preferred day of the month to trigger the schedule. This field can be used with preferredTriggerHour for monthly schedules. The last day of the month is used for numbers larger than the actual number of days in the month. This field is available as specified by the template ( scheduleTemplateId  |
| preferredTriggerDayOfWeek | string | No | The preferred day of the week to trigger the schedule. This field can be used with preferredTriggerHour for weekly schedules. This field is available as specified by the template ( scheduleTemplateId ). The template can specify this field as optional or required, and optionally provides a default va |
| preferredTriggerHour | string | No | The preferred two-digit hour of the day to trigger the schedule. This field is available as specified by the template ( scheduleTemplateId ). The template can specify this field as optional or required, and optionally provides a default value. Format: UTC hhZ For example, the following represents 11 |
| scheduleEndDate | string | No | The timestamp on which the report generation (subscription) ends. After this date, the schedule status becomes INACTIVE . Use this field, if available, to end the schedule in the future. This value must be later than scheduleStartDate (if supplied). This field is available as specified by the templa |
| scheduleName | string | No | The schedule name assigned by the user for the created schedule. |
| scheduleStartDate | string | No | The timestamp to start generating the report. After this timestamp, the schedule status becomes active until either the scheduleEndDate occurs or the scheduleTemplateId becomes inactive. Use this field, if available, to start the schedule in the future but before the scheduleEndDate (if supplied). T |
| scheduleTemplateId | string | No | The unique identifier of the template to be used for this schedule. Use the getScheduleTemplates method to retrieve the schedule template ID. This method requires a schedule template ID that is ACTIVE . Note: Schedules are currently only available for LMS_ORDER_REPORT . |
| schemaVersion | string | No | The schema version of a schedule. |

## Response
_No documented response fields._
