---
title: getNegativeKeywords
category: Marketing_API
api_name: getNegativeKeywords
method: GET
path: /negative_keyword
---

**Category:** Marketing_API
**API:** getNegativeKeywords

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/negative_keyword

## API Description
This method can be used to retrieve all of the negative keywords for ad groups in priority strategy campaigns that use the Cost Per Click (CPC) funding model. The results can be filtered using the campaign_ids , ad_group_ids , and negative_keyword_status query parameters. Call the getCampaigns method to retrieve a list of current campaign IDs for a seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_ids (query) | string | No | A comma-separated list of ad group IDs. This query parameter is used if the seller wants to retrieve the negative keywords from one or more specific ad groups. The results might not include these ad group IDs if other search conditions exclude them. Use the getAdGroups method to retrieve the ad grou |
| campaign_ids (query) | string | No | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the negative keywords being retrieved. This query parameter is used if the seller wants to retrieve the negative keywords from a specific campaign. The results might not include these campaign IDs if |
| limit (query) | string | No | The number of results, from the current result set, to be returned in a single page. |
| negative_keyword_status (query) | string | No | A comma-separated list of negative keyword statuses. This query parameter is used if the seller wants to filter the search results based on one or more negative keyword statuses. See NegativeKeywordStatusEnum for supported values. |
| offset (query) | string | No | The number of results that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is s |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| negativeKeywords | array<NegativeKeyword> | No | A list of negative keywords returned in the paginated collection. |
| negativeKeywords.adGroupId | string | No | An ad group ID that is generated when an ad group is first created and associated with a campaign. Note: You can call the getAdGroups method to retrieve the ad group IDs for a seller. |
| negativeKeywords.campaignId | string | No | A unique eBay-assigned ID for a campaign. This ID is generated when a campaign is created. |
| negativeKeywords.negativeKeywordId | string | No | A unique eBay-assigned ID for a negative keyword. This keyword ID will be generated for each successfully created negative keyword. |
| negativeKeywords.negativeKeywordMatchType | string | No | A field that defines the match type for the negative keyword. Note: Broad matching of negative keywords is not currently supported. Valid Values: EXACT PHRASE For implementation help, refer to eBay API documentation |
| negativeKeywords.negativeKeywordStatus | string | No | A field that defines the status of the negative keyword. For implementation help, refer to eBay API documentation |
| negativeKeywords.negativeKeywordText | string | No | The text for the negative keyword. |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. This value is returned only if there is an additional page of results to display from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Default: 0 Note: The items in a paginated result set use a zero-based list, where the first item in the list has an offset of 0 . |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. |
| total | integer | No | The total number of result sets in the paginated collection. |
