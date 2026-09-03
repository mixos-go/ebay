---
title: deleteAd
category: Marketing_API
api_name: deleteAd
method: DELETE
path: /ad_campaign/{campaign_id}/ad/{ad_id}
---

**Category:** Marketing_API
**API:** deleteAd

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad/{ad_id}

## API Description
This method removes the specified ad from the specified campaign. Pass the ID of the ad to delete with the ID of the campaign associated with the ad as path parameters to the call. Call getCampaigns to get the current list of the seller's campaign IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. When using the CPC funding model, use the bulkUpdateAdsStatusByListingId method to change the status of ads to ARCHIVED.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad being deleted. Use the getAds method to retrieve ad IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad being deleted. Use the getCampaigns method to retrieve campaign IDs. |

## Response
_No documented response fields._
