---
title: getCampaigns
category: Marketing_API
api_name: getCampaigns
method: GET
path: /ad_campaign
---

**Category:** Marketing_API
**API:** getCampaigns

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign

## API Description
This method retrieves the details for all of the seller's defined campaigns. Request parameters can be used to retrieve a specific campaign, such as the campaign's name, the start and end date, the channel, the status, and the funding model (i.e., Cost Per Sale (CPS) or Cost Per Click (CPC)). You can filter the result set by a campaign name, end date range, start date range, campaign channel, or campaign status. You can also paginate the records returned from the result set using the limit query parameter, and control which records to return using the offset parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_name (query) | string | No | This query parameter specifies the name of the campaign being retrieved. The results are filtered to include only the campaign by the specified name. Use the getCampaigns method to retrieve a list of a seller's campaign names. Note: The results might be null if other filters exclude the campaign wit |
| campaign_status (query) | string | No | This query parameter specifies the status of the campaign(s) being retrieved. Note: The results might not include all the campaigns with this status if other filters exclude them. Valid values: See CampaignStatusEnum Maximum: 1 status |
| campaign_targeting_types (query) | string | No | This query parameter specifies the targeting type of the campaign(s) to be retrieved. The results will be filtered to only include campaigns with the specified targeting type. If not specified, all campaigns matching other filter parameters will be returned. The results might not include these campa |
| channels (query) | string | No | This query parameter specifies the channel for the campaign(s) being retrieved. The results will be filtered to only include campaigns with the specified channel. If not specified, all campaigns matching other filter parameters will be returned. The results might not include these campaigns if other |
| end_date_range (query) | string | No | This query parameter specifies the range of a campaign's end date. The results are filtered to include only campaigns with an end date that is within specified range. Valid format (UTC) : yyyy-MM-ddThh:mm:ssZ..yyyy-MM-ddThh:mm:ssZ (campaign ends within this range) yyyy-MM-ddThh:mm:ssZ.. (campaign en |
| funding_strategy (query) | string | No | This query parameter specifies the funding strategy for the campaign(s) being retrieved. The results will be filtered to only include campaigns with the specified funding model. If not specified, all campaigns matching the other filter parameters will be returned. The results might not include these |
| limit (query) | string | No | This query parameter specifies the maximum number of campaigns to return on a page in the paginated response. Default: 10 Maximum: 500 |
| offset (query) | string | No | This query parameter specifies the number of campaigns to skip in the result set before returning the first report in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the |
| start_date_range (query) | string | No | This query parameter specifies the range of a campaign's start date in which to filter the results. The results are filtered to include only campaigns with a start date that is equal to this date or is within specified range. Valid format (UTC): yyyy-MM-ddThh:mm:ssZ..yyyy-MM-ddThh:mm:ssZ (starts wit |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaigns | array<Campaign> | No | This array contains all of the seller's campaign that match the request criteria. |
| campaigns.alerts | array<Alert> | No | This array contains alert messages for the campaign. |
| campaigns.alerts.alertType | string | No | The type of alert message. For example, an invalid bid percentage. For implementation help, refer to eBay API documentation |
| campaigns.alerts.details | array<AlertDetails> | No | A description of the alert including dimensions and aspects. |
| campaigns.alerts.details.dimension | AlertDimension | No | The dimension information of the alert including keys and values. |
| campaigns.alerts.details.dimension.key | string | No | The key field of the applied dimension. For example, the marketplace Id. For implementation help, refer to eBay API documentation |
| campaigns.alerts.details.dimension.value | string | No | The value field of the applied dimension. For example, if the key is a MARKETPLACE_ID , the value would be from MarketplaceIdEnum . |
| campaigns.alerts.details.aspect | Aspect | No | The aspect information of the alert including keys and values. |
| campaigns.alerts.details.aspect.key | string | No | The type of the aspect. For example, MINIMUM_REQUIRED . For implementation help, refer to eBay API documentation |
| campaigns.alerts.details.aspect.value | string | No | The value of the aspect. For example, if the aspect is a percentage, a value of '2.0' would equal 2%. |
| campaigns.budget | CampaignBudget | No | The allocated budget for the Cost Per Click (CPC) Promoted Listings campaign. Note: This field will only be returned for campaigns using the CPC funding model; it does not apply to the Cost Per Sale (CPS) funding model. |
| campaigns.budget.daily | Budget | No | The daily budget limit for the Cost Per Click (CPC) Promoted Listings campaign. Required if the campaign's funding model is CPC. This will be a dollar value. All clicks using the keywords defined for the campaign will go towards expending the daily budget. Once the daily budget is exceeded for the c |
| campaigns.budget.daily.amount | Amount | No | The allocated budget amount for a CPC Promoted Listings campaign. |
| campaigns.budget.daily.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaigns.budget.daily.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaigns.budget.daily.budgetStatus | string | No | The budget status for a CPC Promoted Listings campaign. For implementation help, refer to eBay API documentation |
| campaigns.campaignCriterion | CampaignCriterion | No | The selection rules (criterion) used to select the listings for a campaign. If you populate the campaignCriterion object in your createCampaign request, ads for the campaign are created by rule for the listings that meet the criteria you specify, and these ads are associated with the campaign. Note: |
| campaigns.campaignCriterion.autoSelectFutureInventory | boolean | No | A field used to indicate whether listings shall be automatically added to, or removed from, a Promoted Listings campaign based on the rules that have been configured for the campaign. If set to true , eBay adds all listings matching the campaign criterion to the campaign, including any new listings  |
| campaigns.campaignCriterion.criterionType | string | No | This enum defines the criterion (selection rule) types. Currently, the only criterion type supported is INVENTORY_PARTITION , and you must specify this value if you manage your items with the Inventory API and you want to include items based on their inventory reference IDs. Do not include this fiel |
| campaigns.campaignCriterion.selectionRules | array<SelectionRule> | No | This container shows all of the rules/inclusion filters used to add listings to the campaign. For information on using the contained fields, see Promoted Listing campaigns . |
| campaigns.campaignCriterion.selectionRules.brands | array<string> | No | An array of product brands. For more details, see Using the selectionRules container . |
| campaigns.campaignCriterion.selectionRules.categoryIds | array<string> | No | This field contains an array of the associated category ID(s). For Item discounts , a single-item array containing the category ID associated with the discounts. Required when used in an Item discount and either specifying a selectionRules container or when inventoryCriterionType is set to INVENTORY |
| campaigns.campaignCriterion.selectionRules.categoryScope | string | No | This enumerated value indicates if the category ID for the item is an identifier for eBay categories or for a seller's eBay store categories. For Promoted Listing campaigns , this field includes the type of the category ID for the item(s) to be included in the campaign. For Item discounts , this fie |
| campaigns.campaignCriterion.selectionRules.listingConditionIds | array<string> | No | A comma-separated list of unique identifiers for the conditions of listings to be included For Promoted Listing campaigns , refer to Add items to the campaign . Up to four IDs can be specified. For Item discounts , refer to Item condition ID and name values . |
| campaigns.campaignCriterion.selectionRules.maxPrice | Amount | No | This container sets the maximum price threshold. For more details, see Using the selectionRules container . |
| campaigns.campaignCriterion.selectionRules.maxPrice.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaigns.campaignCriterion.selectionRules.maxPrice.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaigns.campaignCriterion.selectionRules.minPrice | Amount | No | This container sets the minimum price threshold. For more details, see Using the selectionRules container . |
| campaigns.campaignCriterion.selectionRules.minPrice.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaigns.campaignCriterion.selectionRules.minPrice.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaigns.campaignId | string | No | A unique eBay-assigned ID for a campaign. This ID is generated when a campaign is created. |
| campaigns.campaignName | string | No | A seller-defined name for the campaign. This value must be unique for the seller. You can use any alphanumeric characters in the name, except the less than (&lt;) or greater than (&gt;) characters. Max length: 80 characters |
| campaigns.campaignStatus | string | No | Indicates the status of the campaign, such as RUNNING , PAUSED , and ENDED . For implementation help, refer to eBay API documentation |
| campaigns.campaignTargetingType | string | No | The targeting type of the campaign. This value indicates whether the campaign is a manual targeting or smart targeting ad campaign. For implementation help, refer to eBay API documentation |
| campaigns.channels | array<string> | No | The channel for the campaign. This value indicates whether the campaign is an Onsite or Offsite advertising campaign. Valid Values: ON_SITE OFF_SITE |
| campaigns.endDate | string | No | The date and time the campaign ends, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). If this field is omitted, the campaign will have no defined end date, and will not end until the seller makes a decision to end the campaign with an endCampaign call, or if they update the campaign at a later time with an e |
| campaigns.fundingStrategy | FundingStrategy | No | This container includes parameters that define an ad campaign funding strategy. The set of seller-configurable parameters depends on the selected fundingModel value. Currently, the supported funding models are COST_PER_SALE (CPS) and COST_PER_CLICK (CPC). For onsite ads, the CPC model supports two b |
| campaigns.fundingStrategy.adRateStrategy | string | No | This field is used to set the ad rate strategy for a Cost Per Sale (CPS) campaign. The default value for this field is FIXED . If this field is omitted, the default value will be used. Note: This field is not applicable for Cost Per Click (CPC) or offsite campaigns. For implementation help, refer to |
| campaigns.fundingStrategy.biddingStrategy | string | No | Indicates the bidding strategy for an onsite Cost Per Click (CPC) campaign that uses manual targeting. Note: This field is not applicable for smart targeting campaigns. Valid values are: FIXED When using a fixed bidding strategy, sellers manually assign and adjust keyword bids for the CPC campaign.  |
| campaigns.fundingStrategy.bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. The value specified here is also used to calculate the Promoted Listing |
| campaigns.fundingStrategy.bidPreferences | array<BidPreference> | No | This container indicates the bidding preferences of the campaign, such as the maximum CPC amount. Note: This container is only applicable for smart targeting campaigns. This container is required if the user wants to create a Smart Targeting campaign. |
| campaigns.fundingStrategy.bidPreferences.maxCpc | MaxCpc | No | The maximum amount for which the eBay suggested bid can be adjusted. This value represents the most a seller is willing to pay for each click on their ad. The adjusted bid will never exceed this amount. This field is required for smart targeting campaigns. Note: The maximum cost-per-click has a mini |
| campaigns.fundingStrategy.bidPreferences.maxCpc.amount | Amount | No | The allocated maximum CPC amount for a smart targeting campaign. Both the currency and amount must be specified when allocating the Max CPC. |
| campaigns.fundingStrategy.bidPreferences.maxCpc.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| campaigns.fundingStrategy.bidPreferences.maxCpc.amount.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| campaigns.fundingStrategy.dynamicAdRatePreferences | array<DynamicAdRatePreference> | No | A field that indicates whether a single, user-defined bid percentage (also known as the ad rate ) should be used, or whether eBay should automatically adjust listings to maintain the daily suggested bid percentage. Note: Dynamic adjustment is only applicable when the adRateStrategy is set to DYNAMIC |
| campaigns.fundingStrategy.dynamicAdRatePreferences.adRateAdjustmentPercent | string | No | The percentage above or below (-) the eBay suggested ad rate that a seller is willing to pay. This specifies the maximum and minimum values to which an ad rate can be dynamically adjusted. |
| campaigns.fundingStrategy.dynamicAdRatePreferences.adRateCapPercent | string | No | The maximum value (specified as a percentage) to which the eBay suggested ad rate can be adjusted. The adjusted ad rate will never exceed this percentage. |
| campaigns.fundingStrategy.fundingModel | string | No | Indicates the model that eBay uses to calculate the Promoted Listings fee. For a description of the funding model types, refer to FundingModelTypeEnum . For implementation help, refer to eBay API documentation |
| campaigns.marketplaceId | string | No | The ID of the eBay marketplace where the campaign is hosted. For implementation help, refer to eBay API documentation |
| campaigns.startDate | string | No | The date and time the campaign starts, in UTC format ( yyyy-MM-ddThh:mm:ssZ ). For display purposes, convert this time into the local time of the seller. On the date specified, the service derives the keywords for each listing in the campaign, creates an ad for each listing, and associates each new  |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. Max length : 2048 |
| total | integer | No | The total number of campaigns retrieved in the result set. If no campaigns are found, this field is returned with a value of 0 . |
