---
title: updateBiddingStrategy
category: Marketing_API
api_name: updateBiddingStrategy
method: POST
path: /ad_campaign/{campaign_id}/update_bidding_strategy
---

**Category:** Marketing_API
**API:** updateBiddingStrategy

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/update_bidding_strategy

## API Description
This method allows sellers to change the bidding strategy for a specified Cost Per Click (CPC) campaign that uses manual targeting. Available bidding strategies are: FIXED When using a fixed bidding strategy, sellers manually assign and adjust keyword bids for the CPC campaign. DYNAMIC When using a dynamic bidding strategy, eBay will manage a campaign's keyword bids and automatically update them daily to the suggested bid. Note: For a CPC campaign using dynamic bidding, sellers can continue to manually add keywords for the campaign, but they are no longer able to manually adjust their associated bid values. In order to manually adjust bid values, sellers must use the FIXED bidding strategy. In addition, this method allows sellers to modify the maxCPC value of a smart targeting campaign. Note: This method only applies to the Cost Per Click (CPC) funding model; it does not apply to the Cost Per Sale (CPS) funding model. Refer to Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which the keyword bidding strategy is being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| biddingStrategy | string | No | The new bidding strategy for the specified Cost Per Click (CPC) campaign. For implementation help, refer to eBay API documentation |
| bidPreferences | array<BidPreference> | No | This container indicates the bidding preferences of the campaign, such as the maximum CPC amount. Note: This container is only applicable for smart targeting campaigns. This container is required if the user wants to create a Smart Targeting campaign. |
| bidPreferences.maxCpc | MaxCpc | No | The maximum amount for which the eBay suggested bid can be adjusted. This value represents the most a seller is willing to pay for each click on their ad. The adjusted bid will never exceed this amount. This field is required for smart targeting campaigns. Note: The maximum cost-per-click has a mini |
| bidPreferences.maxCpc.amount | Amount | No | The allocated maximum CPC amount for a smart targeting campaign. Both the currency and amount must be specified when allocating the Max CPC. |
| bidPreferences.maxCpc.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| bidPreferences.maxCpc.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |

## Response
_No documented response fields._
