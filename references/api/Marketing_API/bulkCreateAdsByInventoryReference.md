---
title: bulkCreateAdsByInventoryReference
category: Marketing_API
api_name: bulkCreateAdsByInventoryReference
method: POST
path: /ad_campaign/{campaign_id}/bulk_create_ads_by_inventory_reference
---

**Category:** Marketing_API
**API:** bulkCreateAdsByInventoryReference

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/bulk_create_ads_by_inventory_reference

## API Description
This method adds multiple listings that are managed with the Inventory API to an existing Promoted Listings campaign. For general strategy campaigns using the Cost Per Sale (CPS) model, bulk ads may be directly created for the listing. For each listing specified in the request, this method: Creates an ad for the listing. Sets the bid percentage (also known as the ad rate ) for the ads created. Associates the ads created with the specified campaign. To create ads for a listing, specify their inventoryReferenceId and inventoryReferenceType , plus the bidPercentage for the ad in the payload of the request. Specify the campaign to which you want to associate the ads using the campaign_id path parameter. Note: This method only applies to the Cost Per Sale (CPS) funding model; it does not apply to the Cost Per Click (CPC) funding model. See Funding Models in the Promoted Listings Playbook for more information. Use createCampaign to create a new campaign and use getCampaigns to get a list of existing campaigns.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which to associated the ads being created. Use the getCampaigns method to retrieve campaign IDs. |
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
| responses | array<CreateAdsByInventoryReferenceResponse> | No | This array displays the list of ads that were successfully created. For any ads that were not created successfully, the errors array may provide more detail about why creation of one or more ads failed. |
| responses.adGroupId | string | No | A unique eBay-assigned ID for an ad group in a priority strategy campaign that uses the Cost Per Click (CPC) funding model. Note: This field will always be returned for campaigns that use the CPC funding model. It will not be returned for campaigns that use the Cost Per Sale (CPS) funding model. |
| responses.ads | array<AdReference> | No | A list of ad IDs. An ad ID is generated for each successfully created ad. |
| responses.ads.adId | string | No | A unique eBay-assigned ID for an ad. This ID is generated when an ad is created. |
| responses.ads.href | string | No | The getAd URI of an ad. You can use this URI to retrieve the ad. |
| responses.errors | array<Error> | No | An array of errors or warnings associated with the create-ads request. |
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
| responses.inventoryReferenceId | string | No | An ID that identifies a single-item listing or multiple-variation listing that is managed with the Inventory API . The inventory reference ID is a seller-defined value that can be either an SKU for a single-item listing or an inventoryItemGroupKey for a multiple-value listing. |
| responses.inventoryReferenceType | string | No | Indicates the type of item the inventoryReferenceId references. The item can be either an INVENTORY_ITEM or an INVENTORY_ITEM_GROUP . For implementation help, refer to eBay API documentation |
| responses.statusCode | integer | No | An HTTP status code that indicates the response-status of the request. Check this code to see if the ads were successfully created. |
