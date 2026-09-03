---
title: updateAdGroup
category: Marketing_API
api_name: updateAdGroup
method: PUT
path: /ad_campaign/{campaign_id}/ad_group/{ad_group_id}
---

**Category:** Marketing_API
**API:** updateAdGroup

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group/{ad_group_id}

## API Description
This method updates the ad group associated with a campaign. With this method, you can modify the default bid for the ad group, change the state of the ad group, or change the name of the ad group. Pass the ad_group_id you want to update as a URI parameter, and configure the adGroupStatus and defaultBid in the request payload. Call getAdGroup to retrieve the current default bid and status of the ad group that you would like to update.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad group that is being updated. Use the getAdGroups method to retrieve ad group IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which the ad group is being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupStatus | string | No | An enumeration value representing the current status of the ad group. If the status of the ad is currently ACTIVE , you can change status to PAUSED or ARCHIVED . If ad group is currently in PAUSED status, you can change the status back to ACTIVE . Ads that are currently in ARCHIVED status cannot be  |
| defaultBid | Amount | No | A bid amount that applies to all of the keywords in an ad group that do not have individual bids. |
| defaultBid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| defaultBid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| name | string | No | The updated name for the specified ad group. |

## Response
_No documented response fields._
