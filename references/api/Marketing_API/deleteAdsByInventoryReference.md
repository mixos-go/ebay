---
title: deleteAdsByInventoryReference
category: Marketing_API
api_name: deleteAdsByInventoryReference
method: POST
path: /ad_campaign/{campaign_id}/delete_ads_by_inventory_reference
---

**Category:** Marketing_API
**API:** deleteAdsByInventoryReference

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/delete_ads_by_inventory_reference

## API Description
This method works with listings that are managed with the Inventory API . The method deletes ads using a list of seller-defined inventory reference IDs, used with the Inventory API, that are associated with the specified campaign ID. Specify the campaign ID (as a path parameter) and a list of inventoryReferenceId and inventoryReferenceType pairs to be deleted. Call getCampaigns to get a list of the seller's current campaign IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. When using the CPC funding model, use the bulkUpdateAdsStatusByInventoryReference method to change the status of ads to ARCHIVED.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ads being deleted. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| inventoryReferenceType | string | No | This enumerated value indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or an INVENTORY_ITEM_GROUP . For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adIds | array<string> | No | A list of ad IDs. Only one ad can be deleted per operation and only one adId value will be returned. |
