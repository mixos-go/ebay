---
title: suggestBids
category: Marketing_API
api_name: suggestBids
method: POST
path: /ad_campaign/{campaign_id}/ad_group/{ad_group_id}/suggest_bids
---

**Category:** Marketing_API
**API:** suggestBids

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad_group/{ad_group_id}/suggest_bids

## API Description
This method allows sellers to retrieve the suggested bids for input keywords and match type.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad group containing the keywords for which the bid suggestions will be provided. Use the getAdGroups method to retrieve ad group IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the keywords for which bid suggestions will be provided. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| keywords | array<KeywordRequest> | No | An array of keywords for which bids will be required. Maximum number of keywords: 500 |
| keywords.keywordText | string | No | The text of the keyword. Keywords are not case sensitive and compound words can be used without additional encoding (for example, tennis ball). You can use the getKeywords method to retrieve keyword values currently associated with the specified ad group. Maximum number of characters: 100 Maximum nu |
| keywords.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| suggestedBids | array<SuggestedBids> | No | A list of bids in the paginated collection. |
| suggestedBids.keywordText | string | No | The text for the keyword. |
| suggestedBids.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |
| suggestedBids.proposedBid | ProposedBid | No | The suggested bid associated with the keyword. |
| suggestedBids.proposedBid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| suggestedBids.proposedBid.rangeEnd | string | No | The end of the range specified for the bid. |
| suggestedBids.proposedBid.rangeStart | string | No | The start of the range specified for the bid. |
| suggestedBids.proposedBid.value | string | No | The value of the proposed bid. |
