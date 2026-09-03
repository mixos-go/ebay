---
title: getAdGroups
category: Marketing_API
api_name: getAdGroups
method: GET
path: /ad_campaign/{campaign_id}/ad_group
---

**Category:** Marketing_API
**API:** getAdGroups

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group

## API Description
This method retrieves ad groups for the specified campaigns. Each campaign can only have one ad group. In the request, supply the campaign_ids as path parameters. Call getCampaigns to retrieve a list of the current campaign IDs for a seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_status (query) | string | No | A comma-separated list of ad group statuses. The results will be filtered to only include the given statuses of the ad group. See AdGroupStatusEnum for supported values. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad groups being retrieved. Use the getCampaigns method to retrieve campaign IDs. |
| limit (query) | string | No | The number of results, from the current result set, to be returned in a single page. |
| offset (query) | string | No | The number of results that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is s |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroups | array<AdGroup> | No | The details of existing ad groups, such as the name, ID, and status of the ad groups. |
| adGroups.adGroupId | string | No | A unique eBay-assigned ID for an ad group in a campaign that uses the Cost Per Click (CPC) funding model. |
| adGroups.adGroupStatus | string | No | An enumeration value representing the current status of the ad group. Valid Values: ACTIVE PAUSED ARCHIVED For implementation help, refer to eBay API documentation |
| adGroups.defaultBid | Amount | No | A bid amount that applies to all of the keywords in an ad group that do not have individual bids. For all keywords without individual bids, the default bid is the amount that the seller will pay per click for the listings in the ad group in the promoted listings campaign. Valid Values : 0.5, 0.75 |
| adGroups.defaultBid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| adGroups.defaultBid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| adGroups.name | string | No | The seller-defined name of the ad group. |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. This value is returned only if there is an additional page of results to display from the result set. |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Default: 0 Note: The items in a paginated result set use a zero-based list, where the first item in the list has an offset of 0 . |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. |
| total | integer | No | The total number of items retrieved in the result set. Note: If no items are found, this field is returned with a value of 0 . |
