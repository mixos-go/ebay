---
title: getEmailCampaigns
category: Marketing_API
api_name: getEmailCampaigns
method: GET
path: /email_campaign
---

**Category:** Marketing_API
**API:** getEmailCampaigns

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign

## API Description
This method retrieves a list of email campaigns from a seller's eBay store. Users can filter the results by email campaign type , email campaign status , and marketplace ID using the q query parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | The maximum number of email campaigns returned in a page. Min value : 1 Max value : 200 |
| offset (query) | string | No | The number of results to skip in a pagination query. This value cannot be less than zero. Default value : 0 |
| q (query) | string | No | This field contains filter criteria for the results returned. Filter by email campaign type , email campaign status , and marketplace ID . For example, setting q=campaignType:WELCOME,ITEM_SHOWCASE will return only Welcome and Item Showcase email campaigns. Note: At least one campaignType value must  |
| sort (query) | string | No | The criteria for sorting email campaign results. See ItemSortEnum for sorting options and their enum values. Default : NEWLY_LISTED |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaigns | array<CampaignDTO> | No | A list of email campaigns that match the search criteria. |
| campaigns.audiences | array<CampaignAudience> | No | The audiences that the email campaign is being sent to. See AudienceTypeEnum for a list of audience types. |
| campaigns.audiences.audienceType | string | No | This enum value indicates the audience type. For the complete list of audience types and their associated enum values, see AudienceTypeEnum . For implementation help, refer to eBay API documentation |
| campaigns.audiences.code | string | No | The unique code for an audience. |
| campaigns.audiences.name | string | No | The display name for an audience. |
| campaigns.creationDate | string | No | The date and time that the email campaign was created, given in UTC format. |
| campaigns.emailCampaignId | string | No | The unique eBay identifier for the email campaign assigned automatically when the email campaign is created. |
| campaigns.emailCampaignStatus | string | No | The email campaign status. See EmailCampaignStatusEnum for information on statuses. For implementation help, refer to eBay API documentation |
| campaigns.emailCampaignType | string | No | The email campaign type. See CampaignTypeEnum for definitions of email campaign types. For implementation help, refer to eBay API documentation |
| campaigns.marketplaceId | string | No | The eBay marketplace where the email campaign is active. |
| campaigns.modificationDate | string | No | The date and time the email campaign was last modified, given in UTC format. |
| campaigns.scheduleDate | string | No | The date and time that the email campaign newsletter is scheduled to send, given in UTC format. |
| campaigns.scheduleDateType | string | No | The schedule type used for sending the email campaign. See ScheduleDateTypeEnum for available schedule types. For implementation help, refer to eBay API documentation |
| campaigns.sentDate | string | No | The date and time that the email campaign was last sent, given in UTC format. |
| campaigns.subject | string | No | The email campaign subject line.. |
| href | string | No | The URL to the current page of store email campaigns. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of store email campaigns to return on a page from the result set. |
| next | string | No | The URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | This value indicates the offset used for current page of store email campaigns being returned. |
| prev | string | No | The URI for the previous page of results. This is returned if there is a previous page of results from the result set. |
| total | integer | No | Total number of available results returned under the filter criteria submitted in the request. |
