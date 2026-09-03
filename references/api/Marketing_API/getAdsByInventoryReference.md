---
title: getAdsByInventoryReference
category: Marketing_API
api_name: getAdsByInventoryReference
method: GET
path: /ad_campaign/{campaign_id}/get_ads_by_inventory_reference
---

**Category:** Marketing_API
**API:** getAdsByInventoryReference

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/get_ads_by_inventory_reference

## API Description
This method retrieves Promoted Listings ads associated with listings that are managed with the Inventory API from the specified campaign. Supply the campaign_id as a path parameter and use query parameters to specify the inventory_reference_id and inventory_reference_type pairs. In the Inventory API, an inventory reference ID is either a seller-defined SKU value or an inventoryItemGroupKey (a seller-defined ID for an inventory item group, which is an entity that's used in the Inventory API to create a multiple-variation listing). To indicate a listing managed by the Inventory API, you must always specify both an inventory_reference_id and the associated inventory_reference_type . Call getCampaigns to retrieve all of the seller's the current campaign IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ads being retrieved. Use the getCampaigns method to retrieve campaign IDs. |
| inventory_reference_id (query) | string | Yes | This query parameter specifies the unique identifier of a single-item listing or a multi-variation listing. To retrieve an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To retrieve an ad fo |
| inventory_reference_type (query) | string | Yes | This query parameter specifies the type of the item the inventory_reference_id references. See InventoryReferenceType for supported values. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ads | array<Ad> | No | A list of ad IDs. An ad ID is generated for each successfully created ad. |
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
