---
title: getScheduleTemplate
category: Feed_API
api_name: getScheduleTemplate
method: GET
path: /schedule_template/{schedule_template_id}
---

**Category:** Feed_API
**API:** getScheduleTemplate

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/schedule_template/{schedule_template_id}

## API Description
This method retrieves the details of the specified template. Specify the template to retrieve using the schedule_template_id path parameter. Use the getScheduleTemplates method to find a schedule template if you do not know the schedule_template_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| schedule_template_id (path) | string | Yes | This path parameter is the unique identifier of the schedule template being retrieved. Use the getScheduleTemplates method to retrieve schedule template IDs. Note: Template schedules are currently only available for LMS_ORDER_REPORT . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The feed type of the schedule template. Note: When calling createSchedule and updateSchedule methods you must match the feed type specified by the schedule template (this feedType). |
| frequency | string | No | This field specifies how often the schedule is generated. If set to HALF_HOUR or ONE_HOUR , you cannot set a preferredTriggerHour using createSchedule or updateSchedule . For implementation help, refer to eBay API documentation |
| name | string | No | The template name provided by the template. |
| scheduleTemplateId | string | No | The ID of the template. Use this ID to create a schedule based on the properties of this schedule template. |
| status | string | No | The present status of the template. You cannot create or modify a schedule using a template with an INACTIVE status. For implementation help, refer to eBay API documentation |
| supportedConfigurations | array<SupportedConfiguration> | No | An array of the configuration supported by this template. |
| supportedConfigurations.defaultValue | string | No | The default value for the property. If a value is omitted from the schedule and a default value is supplied, the default value is used. |
| supportedConfigurations.property | string | No | Properties supported by the template. Properties can include the following: scheduleStartDate: The timestamp that the report generation (subscription) begins. After this timestamp, the schedule status becomes active until either the scheduleEndDate occurs or the scheduleTemplate becomes inactive. Fo |
| supportedConfigurations.usage | string | No | Whether the specified property is REQUIRED or OPTIONAL. For implementation help, refer to eBay API documentation |
