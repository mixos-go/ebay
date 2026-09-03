---
title: getAdGroup
category: Marketing_API
api_name: getAdGroup
method: GET
path: /ad_campaign/{campaign_id}/ad_group/{ad_group_id}
---

**Category:** Marketing_API
**API:** getAdGroup

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group/{ad_group_id}

## API Description
This method retrieves the details of a specified ad group, such as the ad group’s default bid and status. In the request, specify the campaign_id and ad_group_id as path parameters. Call getCampaigns to retrieve a list of the current campaign IDs for a seller and call getAdGroups for the ad group ID of the ad group you wish to retrieve.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad group being retrieved. Use the getAdGroups method to retrieve ad group IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad group being retrieved. Use the getCampaigns method to retrieve campaign IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | A unique eBay-assigned ID for an ad group in a campaign that uses the Cost Per Click (CPC) funding model. |
| adGroupStatus | string | No | An enumeration value representing the current status of the ad group. Valid Values: ACTIVE PAUSED ARCHIVED For implementation help, refer to eBay API documentation |
| defaultBid | Amount | No | A bid amount that applies to all of the keywords in an ad group that do not have individual bids. For all keywords without individual bids, the default bid is the amount that the seller will pay per click for the listings in the ad group in the promoted listings campaign. Valid Values : 0.5, 0.75 |
| defaultBid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| defaultBid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| name | string | No | The seller-defined name of the ad group. |
