---
title: getScheduleTemplates
category: Feed_API
api_name: getScheduleTemplates
method: GET
path: /schedule_template
---

**Category:** Feed_API
**API:** getScheduleTemplates

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/schedule_template

## API Description
This method retrieves an array containing the details and status of all schedule templates based on the specified feed_type . Use this method to find a schedule template if you do not know the schedule_template_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feed_type (query) | string | Yes | The feed type of the schedule templates to retrieve. Note: Schedules are currently only available for LMS_ORDER_REPORT . |
| limit (query) | string | No | The maximum number of schedule templates that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. Note: This feature employs a zero-based list, where the first item in the list has an offset of 0 |
| offset (query) | string | No | The number of schedule templates to skip in the result set before returning the first template in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the r |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of schedule templates to return per page, from the result set. A result set is the complete set of schedule templates returned by the method. Note: Though this parameter is not required to be submitted in the requ |
| next | string | No | The path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The path to the call URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| scheduleTemplates | array<ScheduleTemplateResponse> | No | An array of the schedule templates on this page. An empty array is returned if the filter criteria excludes all tasks. |
| scheduleTemplates.feedType | string | No | The feed type of the schedule template. Note: When calling createSchedule and updateSchedule methods you must match the feed type specified by the schedule template (this feedType). |
| scheduleTemplates.frequency | string | No | This field specifies how often the schedule is generated. If set to HALF_HOUR or ONE_HOUR , you cannot set a preferredTriggerHour using createSchedule or updateSchedule . For implementation help, refer to eBay API documentation |
| scheduleTemplates.name | string | No | The template name provided by the template. |
| scheduleTemplates.scheduleTemplateId | string | No | The ID of the template. Use this ID to create a schedule based on the properties of this schedule template. |
| scheduleTemplates.status | string | No | The present status of the template. You cannot create or modify a schedule using a template with an INACTIVE status. For implementation help, refer to eBay API documentation |
| scheduleTemplates.supportedConfigurations | array<SupportedConfiguration> | No | An array of the configuration supported by this template. |
| scheduleTemplates.supportedConfigurations.defaultValue | string | No | The default value for the property. If a value is omitted from the schedule and a default value is supplied, the default value is used. |
| scheduleTemplates.supportedConfigurations.property | string | No | Properties supported by the template. Properties can include the following: scheduleStartDate: The timestamp that the report generation (subscription) begins. After this timestamp, the schedule status becomes active until either the scheduleEndDate occurs or the scheduleTemplate becomes inactive. Fo |
| scheduleTemplates.supportedConfigurations.usage | string | No | Whether the specified property is REQUIRED or OPTIONAL. For implementation help, refer to eBay API documentation |
| total | integer | No | The total number of schedule templates that match the input criteria. |
