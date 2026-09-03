---
title: updateAdRateStrategy
category: Marketing_API
api_name: updateAdRateStrategy
method: POST
path: /ad_campaign/{campaign_id}/update_ad_rate_strategy
---

**Category:** Marketing_API
**API:** updateAdRateStrategy

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/update_ad_rate_strategy

## API Description
This method updates the ad rate strategy for an existing rules-based general strategy ad campaign that uses the Cost Per Sale (CPS) funding model. Specify the campaign_id as a path parameter. You can retrieve the campaign IDs for a seller by calling the getCampaigns method. Note: This method only applies to the CPS funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which the ad rate strategy is being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adRateStrategy | string | No | This field is used to change the current ad rate strategy for a Cost Per Sale (CPS) campaign. It is not needed if the ad rate strategy is not being changed for the campaign. Note: This field is not applicable for offsite campaigns. For implementation help, refer to eBay API documentation |
| bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. The value specified here is also used to calculate the Promoted Listing |
| dynamicAdRatePreferences | array<DynamicAdRatePreference> | No | A field that indicates whether a single, user-defined bid percentage (also known as the ad rate ) should be used, or whether eBay should automatically adjust listings to maintain the daily suggested bid percentage. Note: Dynamic adjustment is only applicable when the adRateStrategy is set to DYNAMIC |
| dynamicAdRatePreferences.adRateAdjustmentPercent | string | No | The percentage above or below (-) the eBay suggested ad rate that a seller is willing to pay. This specifies the maximum and minimum values to which an ad rate can be dynamically adjusted. |
| dynamicAdRatePreferences.adRateCapPercent | string | No | The maximum value (specified as a percentage) to which the eBay suggested ad rate can be adjusted. The adjusted ad rate will never exceed this percentage. |

## Response
_No documented response fields._
