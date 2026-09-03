---
title: bulkDeleteAdsByInventoryReference
category: Marketing_API
api_name: bulkDeleteAdsByInventoryReference
method: POST
path: /ad_campaign/{campaign_id}/bulk_delete_ads_by_inventory_reference
---

**Category:** Marketing_API
**API:** bulkDeleteAdsByInventoryReference

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/bulk_delete_ads_by_inventory_reference

## API Description
This method works with listings created with the Inventory API . The method deletes a set of ads, as specified by a list of inventory reference IDs, from the specified campaign. Inventory reference IDs are seller-defined IDs that are used with the Inventory API . Pass the campaign_id as a path parameter and populate the payload with a list of inventoryReferenceId and inventoryReferenceType pairs that you want to delete. Get the campaign IDs for a seller by calling getCampaigns and call getAds to get a list of the seller's inventory reference IDs. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which to delete a set of ads. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<DeleteAdsByInventoryReferenceRequest> | No | A list of inventory referenceID and inventory reference type pairs that specify the set of ads to remove in bulk. |
| requests.inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| requests.inventoryReferenceType | string | No | This enumerated value indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or an INVENTORY_ITEM_GROUP . For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<DeleteAdsByInventoryReferenceResponse> | No | An array of the ads that were deleted by the bulkDeleteAdsByInventoryReference request, including information associated with each individual delete request. |
| responses.adIds | array<string> | No | The unique identifier of the ad that was deleted, or the ad that the seller attempted to delete. Note: Although the field name is plural and it is an array, only one ad ID will be returned here since there can be only one ad per listing. |
| responses.errors | array<Error> | No | The container for the errors associated with the request. |
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
| responses.inventoryReferenceId | string | No | The inventory reference ID is a seller-defined SKU value for a single-item listing, or a seller-defined identifier for an inventory item group. Both of these values are defined when using the Inventory API, and an inventory item group is used to create a multiple-variation listing. |
| responses.inventoryReferenceType | string | No | The enumeration value returned here indicates if the ad was for a single-variation listing or a multiple-variation listing. For implementation help, refer to eBay API documentation |
| responses.statusCode | integer | No | An HTTP status code indicating if the corresponding ad was successfully deleted or not. 200 Successful should be returned for successfully deleted ads. Note: A status code is returned for each ad that the seller deletes, or attempts to delete. |
