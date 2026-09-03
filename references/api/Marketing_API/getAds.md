---
title: getAds
category: Marketing_API
api_name: getAds
method: GET
path: /ad_campaign/{campaign_id}/ad
---

**Category:** Marketing_API
**API:** getAds

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/ad

## API Description
This method retrieves Promoted Listings ads that are associated with listings created with either the Trading API or the Inventory API . The method retrieves ads related to the specified campaign. Specify the Promoted Listings campaign to target with the campaign_id path parameter. Because of the large number of possible results, you can use query parameters to paginate the result set by specifying a limit , which dictates how many ads to return on each page of the response. You can also specify how many ads to skip in the result set before returning the first result using the offset path parameter. Call getCampaigns to retrieve the current campaign IDs for the seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ad_group_ids (query) | string | No | A comma-separated list of ad group IDs. The results will be filtered to only include active ads for these ad groups. Use the getAdGroups method to retrieve the ad group ID for the ad group. Note: This field only applies to the Cost Per Click (CPC) funding model; it does not apply to the Cost Per Sal |
| ad_status (query) | string | No | A comma-separated list of ad statuses. The results will be filtered to only include the given statuses of the ad. If none are provided, all ads are returned. See AdStatusEnum for supported values. |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ads being retrieved. Use the getCampaigns method to retrieve campaign IDs. |
| limit (query) | string | No | Specifies the maximum number of ads to return on a page in the paginated response. Default: 10 Maximum: 500 |
| listing_ids (query) | string | No | A comma-separated list of listing IDs. Note: The response includes only active ads. The results do not include listing IDs that are excluded by other conditions. |
| offset (query) | string | No | Specifies the number of ads to skip in the result set before returning the first ad in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the response con |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ads | array<Ad> | No | The list of ads that matched the request criteria. |
| ads.adGroupId | string | No | A unique eBay-assigned ID for an ad group in a campaign that uses the Cost Per Click (CPC) funding model. This ID is created after a successful createAdGroup call, and all ad groups must be associated with a CPC campaign. |
| ads.adId | string | No | A unique eBay-assigned ID that is generated when the ad is created. |
| ads.adStatus | string | No | The current status of the CPC ad. Valid Values: ACTIVE PAUSED ARCHIVED Note: This type only applies to the Cost Per Click (CPC) funding model; it does not apply to the Cost Per Sale (CPS) funding model. For implementation help, refer to eBay API documentation |
| ads.alerts | array<Alert> | No | An array containing alert messages for the ad. |
| ads.alerts.alertType | string | No | The type of alert message. For example, an invalid bid percentage. For implementation help, refer to eBay API documentation |
| ads.alerts.details | array<AlertDetails> | No | A description of the alert including dimensions and aspects. |
| ads.alerts.details.dimension | AlertDimension | No | The dimension information of the alert including keys and values. |
| ads.alerts.details.dimension.key | string | No | The key field of the applied dimension. For example, the marketplace Id. For implementation help, refer to eBay API documentation |
| ads.alerts.details.dimension.value | string | No | The value field of the applied dimension. For example, if the key is a MARKETPLACE_ID , the value would be from MarketplaceIdEnum . |
| ads.alerts.details.aspect | Aspect | No | The aspect information of the alert including keys and values. |
| ads.alerts.details.aspect.key | string | No | The type of the aspect. For example, MINIMUM_REQUIRED . For implementation help, refer to eBay API documentation |
| ads.alerts.details.aspect.value | string | No | The value of the aspect. For example, if the aspect is a percentage, a value of '2.0' would equal 2%. |
| ads.bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. The value specified here is also used to calculate the Promoted Listing |
| ads.inventoryReferenceId | string | No | An ID that identifies a single-item listing or multiple-variation listing that is managed with the Inventory API . The inventory reference ID is a seller-defined value that can be either an SKU for a single-item listing or an inventoryItemGroupKey for a multiple-value listing. An inventoryItemGroupK |
| ads.inventoryReferenceType | string | No | The enumeration value returned here indicates the type of listing the inventoryReferenceId references. The value returned here will be INVENTORY_ITEM for a single-variation listing, or INVENTORY_ITEM_GROUP for a multiple-variation listing. This field is only returned if the ad is associated with a S |
| ads.listingId | string | No | A unique eBay-assigned ID that is generated when a listing is created. |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. Default : 10 |
| next | string | No | The call URI that can be used to retrieve the next page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be increased to retrieve the next page of results. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first result on the current page. This value can be set in the request with the offset query parameter. If the offset value is not set, it defaults to zero. Default : 0 Note: The items in a paginated result set use a zero-based list  |
| prev | string | No | The call URI that can be used to retrieve the previous page in the result set. Basically, all of the request parameters will remain the same except the offset value, which will be decreased to retrieve the previous page of results. Max length : 2048 |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0 . |
