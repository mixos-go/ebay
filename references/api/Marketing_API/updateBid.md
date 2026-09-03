---
title: updateBid
category: Marketing_API
api_name: updateBid
method: POST
path: /ad_campaign/{campaign_id}/ad/{ad_id}/update_bid
---

**Category:** Marketing_API
**API:** updateBid

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad/{ad_id}/update_bid

## API Description
This method updates the bid percentage (also known as the "ad rate") for the specified ad in the specified campaign. In the request, supply the campaign_id and ad_id as path parameters, and supply the new bidPercentage value in the payload of the call. Call getCampaigns to retrieve a seller's current campaign IDs and call getAds to get their ad IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad for which the bid percentage is being updated. Use the getAds method to retrieve ad IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| bidPercentage | string | No | The updated bid percentage value for the specified ad in the specified campaign. The bid percentage (also known as the ad rate ) is a user-defined value which sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more  |

## Response
_No documented response fields._
