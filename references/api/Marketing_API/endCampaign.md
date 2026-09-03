---
title: endCampaign
category: Marketing_API
api_name: endCampaign
method: POST
path: /ad_campaign/{campaign_id}/end
---

**Category:** Marketing_API
**API:** endCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/end

## API Description
This method ends an active ( RUNNING ) or paused campaign. Specify the campaign you want to end by supplying its campaign ID in a query parameter. Call getCampaigns to retrieve the campaign_id and the campaign status ( RUNNING , PAUSED , ENDED , and so on) for all the seller's campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the RUNNING or PAUSED ad campaign that is being ended. Use the getCampaigns method to retrieve campaign IDs. |

## Response
_No documented response fields._
