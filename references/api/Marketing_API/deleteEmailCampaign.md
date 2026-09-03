---
title: deleteEmailCampaign
category: Marketing_API
api_name: deleteEmailCampaign
method: DELETE
path: /email_campaign/{email_campaign_id}
---

**Category:** Marketing_API
**API:** deleteEmailCampaign

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/{email_campaign_id}

## API Description
This method deletes the email campaign specified by the email_campaign_id path parameter. Call getEmailCampaigns to retrieve all of the seller's email campaigns. Use the email_campaign_id of the desired email campaign in the response as the path parameter for this request.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| email_campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier for the email campaign being deleted. You can retrieve the email campaign IDs for a specified seller using the getEmailCampaigns method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| emailCampaignId | string | No | The unique eBay-assigned ID for the email campaign that is generated when the email campaign is created. |
