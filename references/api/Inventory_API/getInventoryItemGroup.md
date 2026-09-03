---
title: getInventoryItemGroup
category: Inventory_API
api_name: getInventoryItemGroup
method: GET
path: /inventory_item_group/{inventoryItemGroupKey}
---

**Category:** Inventory_API
**API:** getInventoryItemGroup

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/inventory_item_group/{inventoryItemGroupKey}

## API Description
This call retrieves the inventory item group for a given inventoryItemGroupKey value. The inventoryItemGroupKey value is passed in at the end of the call URI.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| inventoryItemGroupKey (path) | string | Yes | This path parameter specifies the unique identifier of the inventory item group being retrieved. This value is assigned by the seller when an inventory item group is created. |

## Response
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
