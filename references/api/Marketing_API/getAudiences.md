---
title: getAudiences
category: Marketing_API
api_name: getAudiences
method: GET
path: /email_campaign/audience
---

**Category:** Marketing_API
**API:** getAudiences

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/audience

## API Description
This method retrieves all available email newsletter audiences for the email campaign type specified by the emailCampaignType path parameter. Use the optional limit and offset path parameters to paginate the results and to control which records are returned, respectively.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| emailCampaignType (query) | string | Yes | The email campaign type to search against. See CampaignTypeEnum for the full list of available email campaign types and associated enum values. |
| limit (query) | string | No | The maximum number of audience groups returned per page in the results set. Min value : 1 Max value : 200 Default value : 100 |
| offset (query) | string | No | The number of results to skip in a pagination query. This value cannot be less than 0. Default value : 0 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| audiences | array<CampaignAudience> | No | An array of audiences available for the specified email campaign type. If no audiences are available, the result will return an empty array. |
| audiences.audienceType | string | No | This enum value indicates the audience type. For the complete list of audience types and their associated enum values, see AudienceTypeEnum . For implementation help, refer to eBay API documentation |
| audiences.code | string | No | The unique code for an audience. |
| audiences.name | string | No | The display name for an audience. |
| href | string | No | The URL to the current page of store email campaign audiences. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of store email campaign audiences to return on a page from the result set. |
| next | string | No | The URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | This value indicates the offset used for the current page of store email campaign audiences returned. |
| prev | string | No | The URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| total | integer | No | The total number of available audiences returned under the query conditions. |
