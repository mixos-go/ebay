---
title: createEmailCampaign
category: Marketing_API
api_name: createEmailCampaign
method: POST
path: /email_campaign
---

**Category:** Marketing_API
**API:** createEmailCampaign

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign

## API Description
This method creates a new email campaign. An eBay store owner can create six different types of email campaigns: Welcome, New products & collections, Coupon, Sale event + markdown, Order discount, and Volume pricing. A successful createEmailCampaign request returns the emailCampaignId assigned to the new email campaign. The fields emailCampaignType , audienceCodes , itemSelectMode , subject , and personalizedMessage are required for all email campaign types. Specific email campaign types have required values for additional fields. For more information on the email campaign types, see the Store Email Campaigns section of the Selling Integration Guide.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The eBay marketplace that the email campaign interfaces with. eBay marketplaces correspond to geographical regions or large submarkets of regions. For example, EBAY-US corresponds to the United States market. See MarketplaceIdEnum for supported values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| audienceCodes | array<string> | No | An array of audience codes for the audiences of the email campaign. At least one audience code is required. There is no upper limit to the number of audience codes. To retrieve seller audiences, call getAudiences . Use the code values in the response to populate audienceCodes . |
| categoryId | string | No | The unique identifier of either an eBay category or a store category. This field is used if a seller wants to apply an email campaign to a specific eBay category or store category. The categoryType determines whether the categoryId value is an eBay category or store category. Use the Taxonomy API to |
| categoryType | string | No | This field must be set when applying an email campaign to a specific eBay category or store category. The enumeration value used indicates which type of category the categoryId belongs to. For implementation help, refer to eBay API documentation |
| emailCampaignType | string | No | The email campaign type of the email campaign being created. There are six email campaigns that a user can create: WELCOME - an email sent automatically to new subscribers. ITEM_SHOWCASE - an email featuring new products & collections that the seller wants to highlight. COUPON - an email containing  |
| itemIds | array<string> | No | An array of unique identifiers for the listings displayed in an email campaign. Used if the seller wishes to select the eBay listings in the email campaign rather than have eBay automatically select them. Call getSellerList to retrieve all seller listings. Each Item result contains an ItemID value.  |
| itemSelectMode | string | No | Determines whether listings featured in an email campaign are selected by the seller or by eBay. If itemSelectMode is set to AUTO , eBay automatically choses listings based on values set for sort , categoryType , categoryId , and priceRange . If itemSelectMode is set to MANUAL , listings are set by  |
| personalizedMessage | string | No | The body of the email campaign. Accepts HTML and CSS. Max length: 1000 |
| priceRange | PriceRange | No | This container is used if the seller wants to apply the email campaign to listings based on a price range. The priceRange container consists of the currency , gte , and lte fields. "gte" stands for "greater than or equal to" and "lte" stands for "less than or equal to". Either gte , lte , or both mu |
| priceRange.currency | string | No | Specifies the currency of the listings in an email campaign using one of the three-digit codes of the CurrencyCodeEnum type. |
| priceRange.gte | number | No | The listings selected will be greater than or equal to this value. The value entered must be given in number format, such as 20.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| priceRange.lte | number | No | The listings selected will be less than or equal to this value. The value entered must be given in number format, such as 100.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| promotionId | string | No | The unique identifier of the discount used for an email campaign if the emailCampaignType is set to COUPON , SALE_EVENT , or ORDER_DISCOUNT . promotionSelectModeEnum must set to MANUAL if a discount is selected. Call getPromotions to retrieve a list of the seller's discounts. Use the promotionId fro |
| promotionSelectModeEnum | string | No | The selection mode for the discount used if the emailCampaignType is set to COUPON , SALE_EVENT , or ORDER_DISCOUNT . If promotionSelectModeEnum is set to AUTO , eBay will choose the discount to include in the email campaign. If set to MANUAL , the seller must specify the discount in the promotionId |
| scheduleDate | string | No | The date and time that the email campaign newsletter will be sent, given in UTC format. Example: 2023-05-20T03:13:35Z This field should be used if the seller wishes to send the email campaign on a future date. If no scheduleDate is set, the email campaign will send once it is created or updated. |
| sort | string | No | The sort rule is used to display the listings featured in the email campaign. Sort rules are only used if itemSelectMode is set to AUTO . If itemSelectMode is MANUAL , listings are displayed in the order in which they are listed in the itemIds array. The following sort rules are available: ENDING_FI |
| subject | string | No | The subject line of the email campaign. Max length: 70 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| emailCampaignId | string | No | The unique eBay-assigned identifier of the email campaign. It is generated automatically when the email campaign is created. This value is returned unless there is an error. |
| emailCampaignStatus | string | No | The status of the email campaign. ACTIVE is returned for email campaigns that have been successfully created but not been sent. SENT is returned for email campaigns that have already been sent. ERROR is returned when an email has not been successfully created. For implementation help, refer to eBay  |
