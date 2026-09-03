---
title: getKeyword
category: Marketing_API
api_name: getKeyword
method: GET
path: /ad_campaign/{campaign_id}/keyword/{keyword_id}
---

**Category:** Marketing_API
**API:** getKeyword

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/keyword/{keyword_id}

## API Description
This method retrieves details on a specific keyword from an ad group within a priority strategy campaign that uses the Cost Per Click (CPC) funding model. In the request, specify the campaign_id and keyword_id as path parameters. Call the getCampaigns method to retrieve a list of current campaign IDs for a seller and call the getKeywords method to retrieve their keyword IDs.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the keyword being retrieved. Use the getCampaigns method to retrieve campaign IDs. |
| keyword_id (path) | string | Yes | This path parameter specifies the unique identifier of the keyword being retrieved. Use the getKeywords method to retrieve keyword IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | This field identifies the ad group that the keyword is associated with. |
| bid | Amount | No | The bid associated with the keyword. This container will not be returned if the keyword does not have a defined bid value. |
| bid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| bid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| keywordId | string | No | The unique identifier of a keyword. |
| keywordStatus | string | No | The status of the keyword. Valid Values: ACTIVE PAUSED ARCHIVED For implementation help, refer to eBay API documentation |
| keywordText | string | No | The text of the keyword. |
| matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |
