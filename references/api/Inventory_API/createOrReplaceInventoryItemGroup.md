---
title: createOrReplaceInventoryItemGroup
category: Inventory_API
api_name: createOrReplaceInventoryItemGroup
method: PUT
path: /inventory_item_group/{inventoryItemGroupKey}
---

**Category:** Inventory_API
**API:** createOrReplaceInventoryItemGroup

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item_group/{inventoryItemGroupKey}

## API Description
Note: Each listing can be revised up to 250 times in one calendar day. If this revision threshold is reached, the seller will be blocked from revising the item until the next calendar day. This call creates a new inventory item group or updates an existing inventory item group. It is up to sellers whether they want to create a complete inventory item group record right from the start, or sellers can provide only some information with the initial createOrReplaceInventoryItemGroup call, and then make one or more additional createOrReplaceInventoryItemGroup calls to complete the inventory item group record. Upon first creating an inventory item group record, the only required elements are the inventoryItemGroupKey identifier in the call URI, and the members of the inventory item group specified through the variantSKUs array in the request payload. Important! Publish offer note: Fields may be optional or conditionally required when calling this method, but become required when publishing the offer to create an active listing. For this method, see Inventory item group fields for a list of fields required to publish an offer. Note: In addition to the authorization header, which is required for all Inventory API calls, this call also requires the Content-Type and Content-Language headers. See the HTTP request headers for more information. In the case of updating/replacing an existing inventory item group, this call does a complete replacement of the existing inventory item group record, so all fields (including the member SKUs) that make up the inventory item group are required, regardless of whether their values changed. So, when replacing/updating an inventory item group record, it is advised that the seller run a getInventoryItemGroup call for that inventory item group to see all of its current values/settings/members before attempting to update the record. And if changes are made to an inventory item group that is part of a live, multiple-variation eBay listing, these changes automatically update the eBay listing. For example, if a SKU value is removed from the inventory item group, the corresponding product variation will be removed from the eBay listing as well. In addition to the required inventory item group identifier and member SKUs, other key information that is set with this call include: Title and description of the inventory item group. The string values provided in these fields will actually become the listing title and listing description of the listing once the first SKU of the inventory item group is published successfully Common aspects that inventory items in the group share Product aspects that vary within each product variation Links to images demonstrating the variations of the product, and these images should correspond to the product aspect that is set with the variesBy.aspectsImageVariesBy field Note: For more information, see Creating and managing inventory item groups .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Language (header) | string | Yes | This header sets the natural language that will be used in the field values of the request payload. For example, the value passed in this header should be en-US for English or de-DE for German. For more information on the Content-Language header, refer to HTTP request headers . |
| inventoryItemGroupKey (path) | string | Yes | This path parameter specifies the unique identifier of the inventory item group being created or updated. This identifier is defined by the seller. This value cannot be changed once it is set. Max Length: 50 |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| aspects | string | No | This is a collection of item specifics (aka product aspects) name-value pairs that are shared by all product variations within the inventory item group. Common aspects for the inventory item group are not immediately required upon creating an inventory item group, but these aspects will be required  |
| description | string | No | The description of the inventory item group. This description should fully describe the product and the variations of the product that are available in the inventory item group, since this description will ultimately become the listing description once the first offer of the group is published. This |
| imageUrls | array<string> | No | An array of one or more links to images for the inventory item group. URLs must use the "HTTPS" protocol. Images can be self-hosted by the seller, or sellers can use the UploadSiteHostedPictures call of the Trading API to upload images to an eBay Picture Server. If successful, the response of the Up |
| inventoryItemGroupKey | string | No | This is the unique identifier of the inventory item group. This identifier is created by the seller when an inventory item group is created. Note: This field is only applicable to the getInventoryItemGroup call and not to the createOrReplaceInventoryItemGroup call. In the createOrReplaceInventoryIte |
| subtitle | string | No | A subtitle is an optional listing feature that allows the seller to provide more information about the product, possibly including keywords that may assist with search results. An additional listing fee will be charged to the seller if a subtitle is used. For more information on using listing subtit |
| title | string | No | The title of the inventory item group. This title will ultimately become the listing title once the first offer of the group is published. This field is not initially required when first creating an inventory item group, but will be required before the first offer of the group is published. Note: Si |
| variantSKUs | array<string> | No | This required container is used to assign individual inventory items to the inventory item group. Multiple SKU values are passed in to this container. If updating an existing inventory item group, the seller should make sure that all member SKU values are passed in, as long as the seller wants that  |
| variesBy | VariesBy | No | This container is used to specify product aspects for which variations within an inventory item group vary, and a complete list of all those variances. For example, t-shirts in an inventory item group may be available in multiple sizes and colors. If this is the case, Color and Size would both be va |
| variesBy.aspectsImageVariesBy | array<string> | No | This container is used if the seller wants to include multiple images to demonstrate how variations within a multiple-variation listing differ. In this string field, the seller will specify the product aspect where the variations of the inventory item group vary, such as color. If Color is specified |
| variesBy.specifications | array<Specification> | No | This container consists of an array of one or more product aspects where each variation differs, and values for each of those product aspects. This container is not immediately required, but will be required before the first offer of the inventory item group is published. If a product aspect is spec |
| variesBy.specifications.name | string | No | This is the name of product variation aspect. Typically, for clothing, typical aspect names are "Size" and "Color" . Product variation aspects are not required immediately upon creating an inventory item group, but these aspects will be required before a multiple-variation listing containing this in |
| variesBy.specifications.values | array<string> | No | This is an array of values pertaining to the corresponding product variation aspect (specified in the name field). Below is a sample of how these values will appear under a specifications container: "specifications": [{ "name": "Size", "values": ["Small", "Medium", "Large"] }, { "name": "Color", "va |
| videoIds | array<string> | No | An array of one or more videoId values for the inventory item group. A video ID is a unique identifier that is automatically created by eBay when a seller successfully uploads a video to eBay using the uploadVideo method of the Media API . For information on supported marketplaces and platforms, as  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| warnings | array<Error> | No | This container will be returned in a call response payload if one or more warnings or errors are triggered when an Inventory API call is made. This container will contain detailed information about the error or warning. |
| warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| warnings.domain | string | No | The name of the domain in which the error or warning occurred. |
| warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific request element(s) most closely associated to the error or warning, if any. |
| warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| warnings.message | string | No | A description of the condition that caused the error or warning. |
| warnings.outputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific response element(s) most closely associated to the error or warning, if any. |
| warnings.parameters | array<ErrorParameter> | No | Various warning and error messages return one or more variables that contain contextual information about the error or waring. This is often the field or value that triggered the error or warning. |
| warnings.parameters.name | string | No | This type contains the name and value of an input parameter that contributed to a specific error or warning condition. |
| warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
