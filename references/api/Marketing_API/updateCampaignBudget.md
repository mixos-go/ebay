---
title: updateCampaignBudget
category: Marketing_API
api_name: updateCampaignBudget
method: POST
path: /ad_campaign/{campaign_id}/update_campaign_budget
---

**Category:** Marketing_API
**API:** updateCampaignBudget

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/update_campaign_budget

## API Description
This method updates the daily budget for a priority strategy campaign that uses the Cost Per Click (CPC) funding model. A click occurs when an eBay user finds and clicks on the seller’s listing (within the search results) after using a keyword that the seller has created for the campaign. For each ad in an ad group in the campaign, each click triggers a cost, which gets subtracted from the campaign’s daily budget. If the cost of the clicks exceeds the daily budget, the Promoted Listings campaign will be paused until the next day. Specify the campaign_id as a path parameter. You can retrieve the campaign IDs for a seller by calling the getCampaigns method. Note: The daily budget for a campaign can only be updated 15 times per day. If this limit is exceeded, an error will occur and you will be blocked from updating the budget until the next day.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which the budget is being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| daily | BudgetRequest | No | The daily budget limit for the Cost Per Click (CPC) Promoted Listings campaign. This will be a dollar value. All clicks using the keywords defined for the campaign will go towards expending the daily budget. Once the daily budget is exceeded for the campaign, all Promoted Listings under the campaign |
| daily.amount | Amount | No | The allocated budget amount for a CPC Promoted Listings campaign. Both the currency and value must be specified. |
| daily.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| daily.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |

## Response
_No documented response fields._
