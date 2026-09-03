---
title: getKeywords
category: Marketing_API
api_name: getKeywords
method: GET
path: /ad_campaign/{campaign_id}/keyword
---

**Category:** Marketing_API
**API:** getKeywords

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/keyword

## API Description
This method can be used to retrieve all of the keywords for ad groups in priority strategy campaigns that use the Cost Per Click (CPC) funding model. In the request, specify the campaign_id as a path parameter. If one or more ad_group_ids are passed in the request body, the keywords for those ad groups will be returned. If ad_group_ids are not passed in the response body, the call will return all the keywords in the campaign. Call the getCampaigns method to retrieve a list of current campaign IDs for a seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_ids (query) | string | No | A comma-separated list of ad group IDs. This query parameter is used if the seller wants to retrieve keywords from one or more specific ad groups. If this query parameter is not used, all keywords that are part of the CPC campaign are returned. Use the getAdGroups method to retrieve the ad group IDs |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the keyword(s) being retrieved. Use the getCampaigns method to retrieve campaign IDs. |
| keyword_status (query) | string | No | A comma-separated list of keyword statuses. The results will be filtered to only include the given statuses of the keyword. If none are provided, all keywords are returned. See KeywordStatusEnum for supported values. |
| limit (query) | string | No | Specifies the maximum number of results to return on a page in the paginated response. Default: 10 Maximum: 500 |
| offset (query) | string | No | Specifies the number of results to skip in the result set before returning the first report in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the resp |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| keywords | array<Keyword> | No | This array contains all of the keywords that match the request criteria. Keywords will be sorted by adGroupId, regardless of whether you searched for keywords across the entire campaign, or if you searched for keywords within one or specific ad groups. |
| keywords.adGroupId | string | No | This field identifies the ad group that the keyword is associated with. |
| keywords.bid | Amount | No | The bid associated with the keyword. This container will not be returned if the keyword does not have a defined bid value. |
| keywords.bid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| keywords.bid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| keywords.keywordId | string | No | The unique identifier of a keyword. |
| keywords.keywordStatus | string | No | The status of the keyword. Valid Values: ACTIVE PAUSED ARCHIVED For implementation help, refer to eBay API documentation |
| keywords.keywordText | string | No | The text of the keyword. |
| keywords.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |
| limit | integer | No | The number of keywords returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. Max length : 2048 |
| total | integer | No | The total number of keywords retrieved in the result set. If no keywords are found, this field is returned with a value of 0 . |
