---
title: getEmailCampaign
category: Marketing_API
api_name: getEmailCampaign
method: GET
path: /email_campaign/{email_campaign_id}
---

**Category:** Marketing_API
**API:** getEmailCampaign

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/email_campaign/{email_campaign_id}

## API Description
This method returns the details of a single email campaign specified by the email_campaign_id path parameter. Call getEmailCampaigns to retrieve a list of all email campaigns from a seller's eBay store.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| email_campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the email campaign being retrieved. Use the getEmailCampaigns method to retrieve a list of email campaign IDs for a seller. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| audiences | array<CampaignAudience> | No | An array of one or more audiences associated with the email campaign. |
| audiences.audienceType | string | No | This enum value indicates the audience type. For the complete list of audience types and their associated enum values, see AudienceTypeEnum . For implementation help, refer to eBay API documentation |
| audiences.code | string | No | The unique code for an audience. |
| audiences.name | string | No | The display name for an audience. |
| categoryId | string | No | The unique identifier of an eBay category or an eBay store category. This field is returned if a seller has applied the email campaign to a specific category. The categoryType value will indicate if the category ID is for an eBay category or an eBay store category. |
| categoryType | string | No | The enumeration value returned here indicates if the categoryId value is the identifier of an eBay category or an eBay store category. This field is returned if a seller has applied the email campaign to a specific category. For implementation help, refer to eBay API documentation |
| creationDate | string | No | The date and time that the email campaign was created, given in UTC format. |
| emailCampaignId | string | No | The unique identifier of the email campaign. |
| emailCampaignStatus | string | No | The email campaign status. See EmailCampaignStatusEnum for a list of valid statuses. For implementation help, refer to eBay API documentation |
| emailCampaignType | string | No | The email campaign type. See CampaignTypeEnum for valid email campaign types. For implementation help, refer to eBay API documentation |
| itemIds | array<string> | No | The listing IDs of the items that were manually added to the email campaign. Only listings added manually by the seller are returned. Returns a null array if no listings were added. |
| itemSelectMode | string | No | The mode used to select the items listed in the email campaign. For implementation help, refer to eBay API documentation |
| marketplaceId | string | No | The eBay marketplace where the email campaign is active. See MarketplaceIdEnum for a list of marketplace IDs. |
| modificationDate | string | No | The date and time the email campaign was last modified, given in UTC format. |
| personalizedMessage | string | No | The body of the email campaign sent to the audience. |
| priceRange | PriceRange | No | The price range and currency set within the email campaign. This container will only return if a price range was set. |
| priceRange.currency | string | No | Specifies the currency of the listings in an email campaign using one of the three-digit codes of the CurrencyCodeEnum type. |
| priceRange.gte | number | No | The listings selected will be greater than or equal to this value. The value entered must be given in number format, such as 20.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| priceRange.lte | number | No | The listings selected will be less than or equal to this value. The value entered must be given in number format, such as 100.00. Either gte , lte , or both must contain a value if the seller wishes to use a price range. |
| promotionId | string | No | The ID of the discount that was assigned to the email campaign. |
| promotionSelectMode | string | No | Indicates whether the listings that the discount was applied to were selected manually or automatically. This field will only return if a discount was applied. For implementation help, refer to eBay API documentation |
| scheduleDate | string | No | The date and time that the email campaign newsletter is scheduled to send, given in UTC format. This field is only returned if the seller set the start of the email campaign to a date in the future. |
| scheduleDateType | string | No | The schedule type of the email campaign. See ScheduleDateTypeEnum . For implementation help, refer to eBay API documentation |
| sentDate | string | No | The date and time that the email campaign was sent, given in UTC format. |
| sort | string | No | The sort rule is used to display the items in the email campaign. If no sort rule was selected, the default will be NEWLY_LISTED . For implementation help, refer to eBay API documentation |
| subject | string | No | The email campaign subject. |
