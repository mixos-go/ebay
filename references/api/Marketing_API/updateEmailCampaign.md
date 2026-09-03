---
title: updateEmailCampaign
category: Marketing_API
api_name: updateEmailCampaign
method: PUT
path: /email_campaign/{email_campaign_id}
---

**Category:** Marketing_API
**API:** updateEmailCampaign

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/{email_campaign_id}

## API Description
This method lets users update an existing email campaign. Pass the emailCampaignId in the request URL and specify the changes to field values in the request payload. Note: You can only update the custom fields of an email campaign. Fixed values, such as the emailCampaignType , cannot be changed. For full specifications of fixed values for each email campaign type, see the createEmailCampaign method documentation.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| email_campaign_id (path) | string | Yes | This path parameter specifies the unique eBay assigned identifier for the email campaign being updated. Use the getEmailCampaigns method to retrieve a list of email campaign IDs for a seller. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| audienceCodes | array<string> | No | An array of audience codes for the audiences of the email campaign. At least one audience code is required. There is no limit to the number of audience codes that may be entered. Example: if the current email campaign contains "audienceCodes": "code1", "code2" and the user wishes to add an audience  |
| categoryId | string | No | The unique identifier of either an eBay category or a store category. This field is used if a seller wants to apply an email campaign to a specific eBay category or store category. The categoryType determines whether the categoryId value is an eBay category or store category. Use the Taxonomy API to |
| categoryType | string | No | This field must be set when applying an email campaign to a specific eBay category or store category. The enumeration value used indicates which type of category the categoryId belongs to. For implementation help, refer to eBay API documentation |
| itemIds | array<string> | No | An array of unique identifiers for the listings displayed in an email campaign. Used if the seller wishes to select the eBay listings in the email campaign rather than have eBay automatically select them. Call getSellerList to retrieve all seller listings. Each Item result contains an ItemID value.  |
| itemSelectMode | string | No | Determines whether listings featured in an email campaign are selected by the seller or by eBay. If itemSelectMode is set to AUTO , eBay automatically choses listings based on values set for sort , categoryType , categoryId , and priceRange . If itemSelectMode is set to MANUAL , listings are set by  |
| personalizedMessage | string | No | The body of the email campaign. Accepts HTML and CSS. The maximum length is 1000 characters |
| priceRange | PriceRange | No | This container is used if the seller wants to apply the email campaign to listings based on a price range. The priceRange container consists of the currency , gte , and lte fields. "gte" stands for "greater than or equal to" and "lte" stands for "less than or equal to". Either gte , lte , or both mu |
| priceRange.currency | string | No | Specifies the currency of the listings in an email campaign using one of the three-digit codes of the CurrencyCodeEnum type. |
| priceRange.gte | number | No | The listings selected will be greater than or equal to this value. The value entered must be given in number format, such as 20.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| priceRange.lte | number | No | The listings selected will be less than or equal to this value. The value entered must be given in number format, such as 100.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| promotionId | string | No | The ID of the discount used for an email campaign if the emailCampaignType is set to COUPON , SALE_EVENT , or ORDER_DISCOUNT , and promotionSelectModeEnum is set to MANUAL . To find a discount, call getPromotions to retrieve a list of the seller's discounts. Use the promotionId from an individual Pr |
| promotionSelectModeEnum | string | No | The selection mode for the discount used. If set to AUTO , eBay will choose the discount to include in the email campaign. If set to MANUAL , the seller must specify the discount in the promotionId field. This field is required if the emailCampaignType is set to COUPON , SALE_EVENT , or ORDER_DISCOU |
| scheduleDate | string | No | The date and time that the email campaign newsletter will be sent, given in UTC format. Example: 2023-05-20T03:13:35Z This field should be used if the seller wishes to send the email campaign on a future date. If no scheduleDate is set, the email campaign will send once it is created or updated. |
| sort | string | No | The sort rule is used to display the listings featured in the email campaign. Sort rules are only used if itemSelectMode is set to AUTO . If itemSelectMode is MANUAL , listings are displayed in the order in which they are listed in the itemIds array. The following sort rules are available: ENDING_FI |
| subject | string | No | The email campaign subject. The maximum length is 70 characters. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| emailCampaignId | string | No | The unique eBay-assigned ID to the email campaign that is generated when the email campaign is created. |
| emailCampaignStatus | string | No | The email campaign status. See EmailCampaignStatusEnum for a list of email campaign statuses and their descriptions. For implementation help, refer to eBay API documentation |
