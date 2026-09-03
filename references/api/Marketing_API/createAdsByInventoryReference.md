---
title: createAdsByInventoryReference
category: Marketing_API
api_name: createAdsByInventoryReference
method: POST
path: /ad_campaign/{campaign_id}/create_ads_by_inventory_reference
---

**Category:** Marketing_API
**API:** createAdsByInventoryReference

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/create_ads_by_inventory_reference

## API Description
This method adds a listing that is managed with the Inventory API to an existing Promoted Listings campaign. For general strategy campaigns using the Cost Per Sale (CPS) funding model, an ad may be directly created for the listing. For each listing specified in the request, this method: Creates an ad for the listing. Sets the bid percentage (also known as the ad rate ) for the ads created. Associates the created ad with the specified campaign. To create an ad for a listing, specify its inventoryReferenceId and inventoryReferenceType , plus the bidPercentage for the ad in the payload of the request. Specify the campaign to associate the ad with using the campaign_id path parameter. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which to associate the newly created ads. Use the getCampaigns method to retrieve campaign IDs |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| adGroupId | string | No | Note: This field is not currently in use. Ad groups are only applicable to priority strategy ad campaigns that use the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. |
| bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. Required if the campaign's funding model is Cost Per Sale (CPS). The va |
| inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| inventoryReferenceType | string | No | This enumerated value indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or an INVENTORY_ITEM_GROUP . For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
