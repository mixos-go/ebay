---
title: getAd
category: Marketing_API
api_name: getAd
method: GET
path: /ad_campaign/{campaign_id}/ad/{ad_id}
---

**Category:** Marketing_API
**API:** getAd

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad/{ad_id}

## API Description
This method retrieves the specified ad from the specified campaign. In the request, supply the campaign_id and ad_id as path parameters. Call getCampaigns to retrieve a list of the seller's current campaign IDs and call getAds to retrieve their current ad IDs.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_id (path) | string | Yes | This path parameter specifies the unique identifier of the ad being retrieved. Use the getAds method to retrieve ad IDs. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad being retrieved. Use the getCampaigns method to retrieve campaign IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | A unique eBay-assigned ID for an ad group in a campaign that uses the Cost Per Click (CPC) funding model. This ID is created after a successful createAdGroup call, and all ad groups must be associated with a CPC campaign. |
| adId | string | No | A unique eBay-assigned ID that is generated when the ad is created. |
| adStatus | string | No | The current status of the CPC ad. Valid Values: ACTIVE PAUSED ARCHIVED Note: This type only applies to the Cost Per Click (CPC) funding model; it does not apply to the Cost Per Sale (CPS) funding model. For implementation help, refer to eBay API documentation |
| alerts | array<Alert> | No | An array containing alert messages for the ad. |
| alerts.alertType | string | No | The type of alert message. For example, an invalid bid percentage. For implementation help, refer to eBay API documentation |
| alerts.details | array<AlertDetails> | No | A description of the alert including dimensions and aspects. |
| alerts.details.dimension | AlertDimension | No | The dimension information of the alert including keys and values. |
| alerts.details.dimension.key | string | No | The key field of the applied dimension. For example, the marketplace Id. For implementation help, refer to eBay API documentation |
| alerts.details.dimension.value | string | No | The value field of the applied dimension. For example, if the key is a MARKETPLACE_ID , the value would be from MarketplaceIdEnum . |
| alerts.details.aspect | Aspect | No | The aspect information of the alert including keys and values. |
| alerts.details.aspect.key | string | No | The type of the aspect. For example, MINIMUM_REQUIRED . For implementation help, refer to eBay API documentation |
| alerts.details.aspect.value | string | No | The value of the aspect. For example, if the aspect is a percentage, a value of '2.0' would equal 2%. |
| bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. The value specified here is also used to calculate the Promoted Listing |
| inventoryReferenceId | string | No | An ID that identifies a single-item listing or multiple-variation listing that is managed with the Inventory API . The inventory reference ID is a seller-defined value that can be either an SKU for a single-item listing or an inventoryItemGroupKey for a multiple-value listing. An inventoryItemGroupK |
| inventoryReferenceType | string | No | The enumeration value returned here indicates the type of listing the inventoryReferenceId references. The value returned here will be INVENTORY_ITEM for a single-variation listing, or INVENTORY_ITEM_GROUP for a multiple-variation listing. This field is only returned if the ad is associated with a S |
| listingId | string | No | A unique eBay-assigned ID that is generated when a listing is created. |
