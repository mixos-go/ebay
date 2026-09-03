---
title: pauseCampaign
category: Marketing_API
api_name: pauseCampaign
method: POST
path: /ad_campaign/{campaign_id}/pause
---

**Category:** Marketing_API
**API:** pauseCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/pause

## API Description
This method pauses an active (RUNNING) campaign. You can restart the campaign by calling resumeCampaign , as long as the campaign's end date is in the future. Note: The listings associated with a paused campaign cannot be added into another campaign. Call getCampaigns to retrieve the campaign_id and the campaign status ( RUNNING , PAUSED , ENDED , and so on) for all the seller's campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the RUNNING ad campaign being paused. Use the getCampaigns method to retrieve campaign IDs. |

## Response
_No documented response fields._
