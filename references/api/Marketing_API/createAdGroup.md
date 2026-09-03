---
title: createAdGroup
category: Marketing_API
api_name: createAdGroup
method: POST
path: /ad_campaign/{campaign_id}/ad_group
---

**Category:** Marketing_API
**API:** createAdGroup

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group

## API Description
This method adds an ad group to an existing priority strategy campaign that uses manual targeting. To create an ad group for a campaign, specify the defaultBid for the ad group in the payload of the request. Then specify the campaign to which the ad group should be associated using the campaign_id path parameter. Each campaign can have one or more associated ad groups.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign to associate with the ad group being created. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| defaultBid | Amount | No | A bid amount that applies to all of the keywords in an ad group that do not have individual bids. |
| defaultBid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| defaultBid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| name | string | No | The seller-defined name of the ad group. |

## Response
_No documented response fields._
