---
title: updateCampaignIdentification
category: Marketing_API
api_name: updateCampaignIdentification
method: POST
path: /ad_campaign/{campaign_id}/update_campaign_identification
---

**Category:** Marketing_API
**API:** updateCampaignIdentification

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/update_campaign_identification

## API Description
This method can be used to change the name of a campaign, as well as modify the start or end dates. Specify the campaign_id you want to update as a URI parameter, and configure the campaignName and startDate in the request payload. If you want to change only the end date of the campaign, specify the current campaign name, set endDate as desired, and set startDate to the actual start date of the campaign. This applies if the campaign status is RUNNING or PAUSED . You can retrieve the startDate using the getCampaign method. Note that if you do not set a new end date in this call, any current endDate value will be set to null . To preserve the currently-set end date, you must specify the value again in your request. Call getCampaigns to retrieve a seller's campaign details, including the campaign ID, campaign name, and the start and end dates of the campaign.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaignName | string | No | The new seller-defined name for the campaign. This value must be unique for the seller. If you don't want to change the name of the campaign, specify the current campaign name in this field. You can use any alphanumeric characters in the name, except the less than (&lt;) or greater than (&gt;) chara |
| endDate | string | No | The date and time the campaign ends, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). If this field is omitted, the campaign will have no defined end date, and will not end until the seller makes a decision to end the campaign with an endCampaign call, or if they update the campaign at a later time with an e |
| startDate | string | No | The new start date for the campaign, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). If the campaign status is RUNNING or PAUSED , the startDate must be specified and must be the actual start date of the campaign, even if you are only changing the endDate . You can retrieve the campaign's startDate using th |

## Response
_No documented response fields._
