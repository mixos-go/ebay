---
title: cloneCampaign
category: Marketing_API
api_name: cloneCampaign
method: POST
path: /ad_campaign/{campaign_id}/clone
---

**Category:** Marketing_API
**API:** cloneCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/clone

## API Description
This method clones (makes a copy of) the specified campaign's campaign criterion . The campaign criterion is a container for the fields that define the criteria for a rule-based campaign. To clone a campaign, supply the campaign_id as a path parameter in your call. There is no request payload. The ID of the newly-cloned campaign is returned in the Location response header. Call getCampaigns to retrieve a seller's current campaign IDs. Requirement: In order to clone a campaign, the campaignStatus must be ENDED and the campaign must define a set of selection rules (it must be a rules-based campaign). Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign being cloned. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaignName | string | No | A seller-defined name for the newly-cloned campaign. This value must be unique for the seller. You can use any alphanumeric characters in the name, except the less than (&lt;) or greater than (&gt;) characters. Max length: 80 characters |
| endDate | string | No | The date and time the campaign ends, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). If this field is omitted, the campaign will have no defined end date, and will not end until the seller makes a decision to end the campaign with an endCampaign call, or if they update the campaign at a later time with an e |
| fundingStrategy | FundingStrategy | No | This container includes parameters that define an ad campaign funding strategy. The set of seller-configurable parameters depends on the selected fundingModel value. |
| fundingStrategy.adRateStrategy | string | No | This field is used to set the ad rate strategy for a Cost Per Sale (CPS) campaign. The default value for this field is FIXED . If this field is omitted, the default value will be used. Note: This field is not applicable for Cost Per Click (CPC) or offsite campaigns. For implementation help, refer to |
| fundingStrategy.biddingStrategy | string | No | Indicates the bidding strategy for an onsite Cost Per Click (CPC) campaign that uses manual targeting. Note: This field is not applicable for smart targeting campaigns. Valid values are: FIXED When using a fixed bidding strategy, sellers manually assign and adjust keyword bids for the CPC campaign.  |
| fundingStrategy.bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. The value specified here is also used to calculate the Promoted Listing |
| fundingStrategy.bidPreferences | array<BidPreference> | No | This container indicates the bidding preferences of the campaign, such as the maximum CPC amount. Note: This container is only applicable for smart targeting campaigns. This container is required if the user wants to create a Smart Targeting campaign. |
| fundingStrategy.bidPreferences.maxCpc | MaxCpc | No | The maximum amount for which the eBay suggested bid can be adjusted. This value represents the most a seller is willing to pay for each click on their ad. The adjusted bid will never exceed this amount. This field is required for smart targeting campaigns. Note: The maximum cost-per-click has a mini |
| fundingStrategy.bidPreferences.maxCpc.amount | Amount | No | The allocated maximum CPC amount for a smart targeting campaign. Both the currency and amount must be specified when allocating the Max CPC. |
| fundingStrategy.bidPreferences.maxCpc.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| fundingStrategy.bidPreferences.maxCpc.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| fundingStrategy.dynamicAdRatePreferences | array<DynamicAdRatePreference> | No | A field that indicates whether a single, user-defined bid percentage (also known as the ad rate ) should be used, or whether eBay should automatically adjust listings to maintain the daily suggested bid percentage. Note: Dynamic adjustment is only applicable when the adRateStrategy is set to DYNAMIC |
| fundingStrategy.dynamicAdRatePreferences.adRateAdjustmentPercent | string | No | The percentage above or below (-) the eBay suggested ad rate that a seller is willing to pay. This specifies the maximum and minimum values to which an ad rate can be dynamically adjusted. |
| fundingStrategy.dynamicAdRatePreferences.adRateCapPercent | string | No | The maximum value (specified as a percentage) to which the eBay suggested ad rate can be adjusted. The adjusted ad rate will never exceed this percentage. |
| fundingStrategy.fundingModel | string | No | Indicates the model that eBay uses to calculate the Promoted Listings fee. For a description of the funding model types, refer to FundingModelTypeEnum . For implementation help, refer to eBay API documentation |
| startDate | string | No | The date and time the cloned campaign starts, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). For display purposes, convert this time into the local time of the seller. On the date specified, the service derives the keywords for each listing in the campaign, creates an ad for each listing, and associates ea |

## Response
_No documented response fields._
