---
title: getSchedules
category: Feed_API
api_name: getSchedules
method: GET
path: /schedule
---

**Category:** Feed_API
**API:** getSchedules

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/schedule

## API Description
This method retrieves an array containing the details and status of all schedules based on the specified feed_type . Use this method to find a schedule if you do not know the schedule_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feed_type (query) | string | Yes | The feed type associated with the schedules being retrieved. Note: Schedules are currently only available for LMS_ORDER_REPORT . |
| limit (query) | string | No | The maximum number of schedules that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. Note: This feature employs a zero-based list, where the first item in the list has an offset of 0 . For ex |
| offset (query) | string | No | The number of schedules to skip in the result set before returning the first schedule in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the response c |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of schedules to return per page, from the result set. A result set is the complete set of schedules returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter |
| next | string | No | The path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The path to the call URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| schedules | array<UserScheduleResponse> | No | An array of the schedules on this page. An empty array is returned if the filter criteria excludes all tasks. |
| schedules.scheduleId | string | No | The ID of the schedule. This ID is generated when the schedule was created by the createSchedule method. |
| schedules.creationDate | string | No | The creation date of the schedule in hours based on the 24-hour Coordinated Universal Time (UTC) clock. |
| schedules.feedType | string | No | The feedType associated with the schedule. |
| schedules.lastModifiedDate | string | No | The date the schedule was last modified. |
| schedules.preferredTriggerDayOfMonth | integer | No | The preferred day of the month to trigger the schedule. This field can be used with preferredTriggerHour for monthly schedules. The last day of the month is used for numbers larger than the number of days in the month. |
| schedules.preferredTriggerDayOfWeek | string | No | The preferred day of the week to trigger the schedule. This field can be used with preferredTriggerHour for weekly schedules. For implementation help, refer to eBay API documentation |
| schedules.preferredTriggerHour | string | No | The preferred two-digit hour of the day to trigger the schedule. Format: UTC hhZ For example, the following represents 11:00 am UTC: 11Z |
| schedules.scheduleEndDate | string | No | The timestamp on which the report generation (subscription) ends. After this date, the schedule status becomes INACTIVE . |
| schedules.scheduleName | string | No | The schedule name assigned by the user for the created schedule. Users assign this name for their reference. |
| schedules.scheduleStartDate | string | No | The timestamp that indicates the start of the report generation. |
| schedules.scheduleTemplateId | string | No | The ID of the template used to create this schedule. |
| schedules.schemaVersion | string | No | The schema version of the feedType for the schedule. |
| schedules.status | string | No | The enumeration value that indicates the state of the schedule. For implementation help, refer to eBay API documentation |
| schedules.statusReason | string | No | The reason the schedule is inactive. For implementation help, refer to eBay API documentation |
| total | integer | No | The total number of schedules that match the input criteria. |
