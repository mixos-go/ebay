---
title: resumeCampaign
category: Marketing_API
api_name: resumeCampaign
method: POST
path: /ad_campaign/{campaign_id}/resume
---

**Category:** Marketing_API
**API:** resumeCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/resume

## API Description
This method resumes a paused campaign, as long as its end date is in the future. Supply the campaign_id for the campaign you want to restart as a query parameter in the request. Call getCampaigns to retrieve the campaign_id and the campaign status ( RUNNING , PAUSED , ENDED , and so on) for all the seller's campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the paused ad campaign that is being resumed. Use the getCampaigns method to retrieve campaign IDs. |

## Response
_No documented response fields._
