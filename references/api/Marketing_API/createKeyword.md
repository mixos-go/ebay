---
title: createKeyword
category: Marketing_API
api_name: createKeyword
method: POST
path: /ad_campaign/{campaign_id}/keyword
---

**Category:** Marketing_API
**API:** createKeyword

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/keyword

## API Description
This method creates keywords using a specified campaign ID for an existing priority strategy campaign that uses manual targeting. In the request, supply the campaign_id as a path parameter. Call the suggestKeywords method to retrieve a list of keyword ideas to be targeted for priority strategy campaigns, and call the getCampaigns method to retrieve a list of current campaign IDs for a seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which a keyword is being created. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | This adGroupId is created when an ad group is first created and associated with a campaign. This is the ad group that the corresponding keyword will be added to. This ad group must be a part of the campaign that is specified in the call URI. Use the getAdGroups method to retrieve the ad group IDs fo |
| bid | Amount | No | This container is used to set the maximum bid for the keyword. Each time a listing is retrieved in search results using this keyword and clicked on, the seller will be charged, at most, this amount. Each click goes toward the daily budget set up for the CPC campaign. If the bid is not provided, then |
| bid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| bid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| keywordText | string | No | The text of the keyword. Keywords are not case sensitive and compound words can be used without additional encoding (for example, tennis ball). Maximum number of characters: 100 Maximum number of words: 10 |
| matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
