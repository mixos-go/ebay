---
title: getNegativeKeyword
category: Marketing_API
api_name: getNegativeKeyword
method: GET
path: /negative_keyword/{negative_keyword_id}
---

**Category:** Marketing_API
**API:** getNegativeKeyword

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/negative_keyword/{negative_keyword_id}

## API Description
This method retrieves details on a specific negative keyword. In the request, specify the negative_keyword_id as a path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| negative_keyword_id (path) | string | Yes | This path parameter specifies the unique identifier for the negative keyword being retrieved. Use the getNegativeKeywords method to retrieve negative keyword IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | An ad group ID that is generated when an ad group is first created and associated with a campaign. Note: You can call the getAdGroups method to retrieve the ad group IDs for a seller. |
| campaignId | string | No | A unique eBay-assigned ID for a campaign. This ID is generated when a campaign is created. |
| negativeKeywordId | string | No | A unique eBay-assigned ID for a negative keyword. This keyword ID will be generated for each successfully created negative keyword. |
| negativeKeywordMatchType | string | No | A field that defines the match type for the negative keyword. Note: Broad matching of negative keywords is not currently supported. Valid Values: EXACT PHRASE For implementation help, refer to eBay API documentation |
| negativeKeywordStatus | string | No | A field that defines the status of the negative keyword. For implementation help, refer to eBay API documentation |
| negativeKeywordText | string | No | The text for the negative keyword. |
