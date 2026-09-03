---
title: deleteCampaign
category: Marketing_API
api_name: deleteCampaign
method: DELETE
path: /ad_campaign/{campaign_id}
---

**Category:** Marketing_API
**API:** deleteCampaign

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}

## API Description
This method deletes the campaign specified by the campaign_id query parameter. Note: You can only delete campaigns that have ended. Call getCampaigns to retrieve the campaign_id and the campaign status ( RUNNING , PAUSED , ENDED , and so on) for all the seller's campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign being deleted. Use the getCampaigns method to retrieve campaign IDs. |

## Response
_No documented response fields._
