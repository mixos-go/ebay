---
title: createCampaign
category: Marketing_API
api_name: createCampaign
method: POST
path: /ad_campaign
---

**Category:** Marketing_API
**API:** createCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign

## API Description
This method can be used to create a Promoted Listings general, priority, or offsite campaign. A Promoted Listings campaign is the structure in which you place the ads or ad group for the listings you wish to promote. Note: Campaigns can only contain ads for a maximum of 50,000 items. General strategy campaigns utilize a Cost Per Sale (CPS) funding model. Sellers can set the ad rate and bidding strategies that are right for their business through the adRateStrategy , biddingStrategy , bidPercentage fields. For more information on general strategy campaigns, see Promoted Listings general strategy campaign flow . Priority strategy campaigns utilize a Cost per Click (CPC) funding model. Sellers can create a daily budget through the budget container and choose what channel that their ads appear on. In addition, priority strategy campaigns give sellers the ability to create ad groups and specify keywords to ensure their ads reach their intended audience. For more information on priority strategy campaigns, see Promoted listings priority strategy campaign flow . Promoted Offsite campaigns give sellers the ability to create their own advertising campaign and promote their eBay listing in leading external search channels. For more information on Promoted Offsite campaigns, see Promoted Offsite . Note: Sellers can use the getAdvertisingEligibility method of the Account API v1 to determine their eligibility status for eBay advertising programs. To create a basic campaign, supply: The user-defined campaign name The start date (and optionally the end date) of the campaign The eBay marketplace on which the campaign is hosted Details on the campaign funding model For details on creating Promoted Listings campaigns and how to select the items to be included in your campaigns, see Promoted Listings campaign creation .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| budget | CampaignBudgetRequest | No | The allocated daily budget for the Cost Per Click (CPC) Promoted Listings campaign. Required if the campaign funding model is CPC. |
| budget.daily | BudgetRequest | No | The daily budget limit for a CPC Promoted Listings campaign. When running an offsite campaign, eBay may spend more or less than the seller's daily budget to capitalize on interested buyers, but will not exceed 2x the daily budget. The average over the course of the campaign will not exceed the provi |
| budget.daily.amount | Amount | No | The allocated budget amount for a CPC Promoted Listings campaign. Both the currency and value must be specified. |
| budget.daily.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| budget.daily.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaignCriterion | CampaignCriterion | No | This container is used if the seller wishes to create one or more rules for a rules-based campaign. If you populate the campaignCriterion object in your createCampaign request, ads for the campaign are created by rule for the listings that meet the criteria you specify, and these ads are associated  |
| campaignCriterion.autoSelectFutureInventory | boolean | No | A field used to indicate whether listings shall be automatically added to, or removed from, a Promoted Listings campaign based on the rules that have been configured for the campaign. If set to true , eBay adds all listings matching the campaign criterion to the campaign, including any new listings  |
| campaignCriterion.criterionType | string | No | This enum defines the criterion (selection rule) types. Currently, the only criterion type supported is INVENTORY_PARTITION , and you must specify this value if you manage your items with the Inventory API and you want to include items based on their inventory reference IDs. Do not include this fiel |
| campaignCriterion.selectionRules | array<SelectionRule> | No | This container shows all of the rules/inclusion filters used to add listings to the campaign. For information on using the contained fields, see Promoted Listing campaigns . |
| campaignCriterion.selectionRules.brands | array<string> | No | An array of product brands. For more details, see Using the selectionRules container . |
| campaignCriterion.selectionRules.categoryIds | array<string> | No | This field contains an array of the associated category ID(s). For Item discounts , a single-item array containing the category ID associated with the discounts. Required when used in an Item discount and either specifying a selectionRules container or when inventoryCriterionType is set to INVENTORY |
| campaignCriterion.selectionRules.categoryScope | string | No | This enumerated value indicates if the category ID for the item is an identifier for eBay categories or for a seller's eBay store categories. For Promoted Listing campaigns , this field includes the type of the category ID for the item(s) to be included in the campaign. For Item discounts , this fie |
| campaignCriterion.selectionRules.listingConditionIds | array<string> | No | A comma-separated list of unique identifiers for the conditions of listings to be included For Promoted Listing campaigns , refer to Add items to the campaign . Up to four IDs can be specified. For Item discounts , refer to Item condition ID and name values . |
| campaignCriterion.selectionRules.maxPrice | Amount | No | This container sets the maximum price threshold. For more details, see Using the selectionRules container . |
| campaignCriterion.selectionRules.maxPrice.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaignCriterion.selectionRules.maxPrice.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaignCriterion.selectionRules.minPrice | Amount | No | This container sets the minimum price threshold. For more details, see Using the selectionRules container . |
| campaignCriterion.selectionRules.minPrice.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaignCriterion.selectionRules.minPrice.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaignName | string | No | A seller-defined name for the campaign. This value must be unique for the seller. You can use any alphanumeric characters in the name, except the less than (&lt;) or greater than (&gt;) characters. Max length: 80 characters |
| campaignTargetingType | string | No | The targeting type of the campaign. This value indicates whether the campaign is a manual targeting or smart targeting campaign. If not value is specified, this field will default to MANUAL . Note: This feature is only supported for on-site campaigns that use the Cost Per Click (CPC) funding model.  |
| channels | array<string> | No | The channel for the campaign. This value indicates whether the advertising campaign is an Onsite or Offsite. If no value is entered, this field will default to ON_SITE . Multiple channels are not supported. Note: Channels is only applicable for campaigns that use the Cost Per Click (CPC) funding mod |
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
| marketplaceId | string | No | The ID of the eBay marketplace where the campaign is hosted. See the MarketplaceIdEnum type to get the appropriate enumeration value for the listing marketplace. For implementation help, refer to eBay API documentation |
| startDate | string | No | The date and time the campaign starts, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). For display purposes, convert this time into the local time of the seller. On the date specified, the service derives the keywords for each listing in the campaign, creates an ad for each listing, and associates each new  |

## Response
_No documented response fields._
