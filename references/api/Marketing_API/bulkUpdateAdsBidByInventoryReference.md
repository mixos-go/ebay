---
title: bulkUpdateAdsBidByInventoryReference
category: Marketing_API
api_name: bulkUpdateAdsBidByInventoryReference
method: POST
path: /ad_campaign/{campaign_id}/bulk_update_ads_bid_by_inventory_reference
---

**Category:** Marketing_API
**API:** bulkUpdateAdsBidByInventoryReference

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/bulk_update_ads_bid_by_inventory_reference

## API Description
This method works with listings created with either the Trading API or the Inventory API . The method updates the bidPercentage values for a set of ads associated with the specified campaign. Specify the campaign_id as a path parameter and supply a set of listing IDs with their associated updated bidPercentage values in the request body. An eBay listing ID is generated when a listing is created with the Trading API. Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which to update the bid percentage for a set of ads. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<CreateAdsByInventoryReferenceRequest> | No | A list of inventory reference ID and inventory reference type pairs, and the bid percentage, which the call uses to create ads in bulk. |
| requests.adGroupId | string | No | Note: This field is not currently in use. Ad groups are only applicable to priority strategy ad campaigns that use the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. |
| requests.bidPercentage | string | No | The user-defined bid percentage (also known as the ad rate ) sets the level that eBay increases the visibility in search results for the associated listing. The higher the bidPercentage value, the more eBay promotes the listing. Required if the campaign's funding model is Cost Per Sale (CPS). The va |
| requests.inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| requests.inventoryReferenceType | string | No | This enumerated value indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or an INVENTORY_ITEM_GROUP . For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<UpdateAdsByInventoryReferenceResponse> | No | A list of inventory references that were processed from the request. |
| responses.ads | array<AdReference> | No | A list of ad IDs and links to retrieve them. |
| responses.ads.adId | string | No | A unique eBay-assigned ID for an ad. This ID is generated when an ad is created. |
| responses.ads.href | string | No | The getAd URI of an ad. You can use this URI to retrieve the ad. |
| responses.errors | array<Error> | No | A container for all of the errors associated with the specified inventory reference ID. |
| responses.errors.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| responses.errors.domain | string | No | Name of the domain containing the service or application. |
| responses.errors.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| responses.errors.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| responses.errors.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| responses.errors.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| responses.errors.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| responses.errors.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| responses.errors.parameters.name | string | No | Name of the entity that threw the error. |
| responses.errors.parameters.value | string | No | A description of the error. |
| responses.errors.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
| responses.inventoryReferenceId | string | No | The reference ID associated with the ad. The reference ID could be a SKU number or Inventory Item Group, depending on value of inventoryReferenceType . |
| responses.inventoryReferenceType | string | No | The inventory reference type associated with the ad. The inventory reference type could be a SKU number or Inventory Item Group. For implementation help, refer to eBay API documentation |
| responses.statusCode | integer | No | An HTTP status code that indicates whether or not the CPS ad was successfully updated. |
