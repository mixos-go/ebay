---
title: suggestBudget
category: Marketing_API
api_name: suggestBudget
method: GET
path: /ad_campaign/suggest_budget
---

**Category:** Marketing_API
**API:** suggestBudget

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/suggest_budget

## API Description
Note: This method is only supported for Promoted Offsite campaigns. Sellers can use the getAdvertisingEligibility method of the Account API v1 to determine if they are eligible for offsite campaigns. This method allows sellers to retrieve the suggested budget for an offsite campaign.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. Note: If a marketplace ID value is not provided, the default value of EBAY_US is used. See MarketplaceIdEnum for supported values. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| suggestedBudget | array<BudgetRecommendationResponse> | No | The suggested allocated daily budget for an offsite campaign. |
| suggestedBudget.budget | CampaignBudget | No | The allocated daily budget for the Cost Per Click (CPC) Promoted Listings campaign. |
| suggestedBudget.budget.daily | Budget | No | The daily budget limit for the Cost Per Click (CPC) Promoted Listings campaign. Required if the campaign's funding model is CPC. This will be a dollar value. All clicks using the keywords defined for the campaign will go towards expending the daily budget. Once the daily budget is exceeded for the c |
| suggestedBudget.budget.daily.amount | Amount | No | The allocated budget amount for a CPC Promoted Listings campaign. |
| suggestedBudget.budget.daily.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| suggestedBudget.budget.daily.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| suggestedBudget.budget.daily.budgetStatus | string | No | The budget status for a CPC Promoted Listings campaign. For implementation help, refer to eBay API documentation |
| suggestedBudget.campaignId | string | No | The unique eBay-assigned ID for a campaign. This ID is generated when a campaign is created. |
| suggestedBudget.channels | array<string> | No | The channel for the campaign. This value indicates whether the campaign is an Onsite or Offsite advertising campaign. Valid Values: ON_SITE OFF_SITE |
