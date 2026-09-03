---
title: createNegativeKeyword
category: Marketing_API
api_name: createNegativeKeyword
method: POST
path: /negative_keyword
---

**Category:** Marketing_API
**API:** createNegativeKeyword

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/negative_keyword

## API Description
This method adds a negative keyword to an existing ad group in a priority strategy campaign that uses manual targeting. Specify the campaignId and adGroupId in the request body, along with the negativeKeywordText and negativeKeywordMatchType . Call the getCampaigns method to retrieve a list of current campaign IDs for a specified seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | This adGroupId is created when an ad group is first created and associated with a campaign. This is the ad group to which the corresponding negative keyword will be added. Use the getAdGroups method to retrieve the ad group IDs for a seller. Required if the negative keyword is being created at the a |
| campaignId | string | No | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the set of negative keywords being created. Use the getCampaigns method to retrieve campaign IDs. Required if the negative keyword is being created at the ad group level. |
| negativeKeywordMatchType | string | No | A field that defines the match type for the negative keyword. Note: Broad matching of negative keywords is not currently supported. Valid Values: EXACT PHRASE For implementation help, refer to eBay API documentation |
| negativeKeywordText | string | No | The negative keyword text. |

## Response
_No documented response fields._
