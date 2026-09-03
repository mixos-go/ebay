---
title: suggestItems
category: Marketing_API
api_name: suggestItems
method: GET
path: /ad_campaign/{campaign_id}/suggest_items
---

**Category:** Marketing_API
**API:** suggestItems

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/suggest_items

## API Description
This method allows sellers to obtain ideas for listings, which can be targeted for Promoted Listings campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which suggestions are being provided. Use the getCampaigns method to retrieve campaign IDs. |
| category_ids (query) | string | No | Specifies the category ID that is used to limit the results. This refers to an exact leaf category (the lowest level in that category and has no children). This field can have one category ID, or a comma-separated list of IDs. To return all category IDs, set to null . Use the getCategorySuggestions  |
| limit (query) | string | No | Specifies the maximum number of campaigns to return on a page in the paginated response. If no value is specified, the default value is used. Default: 10 Minimum: 1 Maximum: 1000 |
| offset (query) | string | No | Specifies the number of campaigns to skip in the result set before returning the first report in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the re |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. This value is returned only if there is an additional page of results to display from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Default: 0 Note: The items in a paginated result set use a zero-based list, where the first item in the list has an offset of 0 . |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. |
| suggestedItems | array<TargetingItems> | No | A list of suggested items in the paginated collection. |
| suggestedItems.bases | array<ItemBasis> | No | The metrics and additional information for the items. |
| suggestedItems.bases.estimatedValue | integer | No | The estimated value of the search impressions for items based on the provided dimensions. Duration: 17 days Total slots: 200 Channel: Dweb, Mweb, Native |
| suggestedItems.bases.metric | string | No | The basis of the statistics. For implementation help, refer to eBay API documentation |
| suggestedItems.listingId | string | No | The listing ID of the targeted item. |
| total | integer | No | The total number of items retrieved in the result set. Note: If no items are found, this field is returned with a value of 0 . |
