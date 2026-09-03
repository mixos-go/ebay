---
title: suggestKeywords
category: Marketing_API
api_name: suggestKeywords
method: POST
path: /ad_campaign/{campaign_id}/ad_group/{ad_group_id}/suggest_keywords
---

**Category:** Marketing_API
**API:** suggestKeywords

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group/{ad_group_id}/suggest_keywords

## API Description
This method allows sellers to retrieve a list of keyword ideas to be targeted for Promoted Listings campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad group for which the keyword suggestions will be provided. Use the getAdGroups method to retrieve ad group IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which keyword suggestions will be provided. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| additionalInfo | array<string> | No | A field used to indicate whether additional information and insight data shall be provided for suggested keywords. Use this array to retrieve keyword insights, including active seller count and search volume. Valid Value: KEYWORD_INSIGHTS |
| exclusions | array<string> | No | A field used to indicate that the keywords already selected by sellers for the specified listing IDs should be filtered out of the response, and only new and unique keyword recommendations shall be returned. Valid Value: ADOPTED_KEYWORDS |
| listingIds | array<string> | No | A set of comma-separated listing IDs for the specific listings you wish to retrieve suggested keywords. Maximum number of listings requested: 300 |
| matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| suggestedKeywords | array<SuggestedKeywords> | No | A list of suggested keywords in the paged collection. Note: A relevancy check with items already present in the ad-group is performed even if item IDs associated with the ad-group are not explicitly passed in the request. |
| suggestedKeywords.additionalInfo | array<AdditionalInfo> | No | A container for the additional information and compiled insight data for suggested keywords. |
| suggestedKeywords.additionalInfo.infoType | string | No | The type of additional information provided for the suggested keyword. Valid Value: KEYWORD_INSIGHTS For implementation help, refer to eBay API documentation |
| suggestedKeywords.additionalInfo.metrics | array<AdditionalInfoData> | No | A list of additional data provided for the suggested keyword. |
| suggestedKeywords.additionalInfo.metrics.metricKey | string | No | The metric used to provide additional information for the suggested keyword. Valid Values: ACTIVE_SELLER_COUNT SEARCH_VOLUME For implementation help, refer to eBay API documentation |
| suggestedKeywords.additionalInfo.metrics.value | string | No | The data provided for the specified metric. Note: All metric data is compiled for the marketplace associated with the specified campaign ID. |
| suggestedKeywords.keywordText | string | No | The text for the keyword. |
| suggestedKeywords.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |
