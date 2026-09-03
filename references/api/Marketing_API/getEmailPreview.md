---
title: getEmailPreview
category: Marketing_API
api_name: getEmailPreview
method: GET
path: /email_campaign/{email_campaign_id}/email_preview
---

**Category:** Marketing_API
**API:** getEmailPreview

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/{email_campaign_id}/email_preview

## API Description
This method returns a preview of the email sent by the email campaign indicated by the email_campaign_id path parameter. Call getEmailCampaigns to obtain a list of email campaigns. Use the emailCampaignId value of the desired email campaign as the email_campaign_id path parameter value. If this call is executed successfully, the response returns a content field that contains the raw HTML code of the email campaign that can then be rendered anywhere. Note: The eBay listings in the email are sorted according to the email campaign sort criteria. The individual listings can change over time, as well. The result of the email preview call can be treated as a snapshot of the email campaign taken at the date and time of the renderDate value found in the results of the call.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| email_campaign_id (path) | string | Yes | This path parameter specifies the unique eBay assigned identifier for the email campaign associated with the preview being retrieved. Use the getEmailCampaigns method to retrieve a list of email campaign IDs for a seller. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| content | string | No | The raw HTML code of the email campaign contents. The client side can use this HTML output directly. Because the contents of an email campaign are subject to change, these contents are a "snapshot" of the email campaign at a specific time and date, indicated by the renderDate field. |
| renderDate | string | No | The date and time when a "snapshot" of the email campaign contents contained in the content result was taken. Given in UTC format. |
