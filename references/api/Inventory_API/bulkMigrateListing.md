---
title: bulkMigrateListing
category: Inventory_API
api_name: bulkMigrateListing
method: POST
path: /bulk_migrate_listing
---

**Category:** Inventory_API
**API:** bulkMigrateListing

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_migrate_listing

## API Description
This call is used to convert existing eBay Listings to the corresponding Inventory API objects. If an eBay listing is successfully migrated to the Inventory API model, new Inventory Location, Inventory Item, and Offer objects are created. For a multiple-variation listing that is successfully migrated, in addition to the three new Inventory API objects just mentioned, an Inventory Item Group object will also be created. If the eBay listing is a motor vehicle part or accessory listing with a compatible vehicle list ( ItemCompatibilityList container in Trading API's Add/Revise/Relist/Verify calls), a Product Compatibility object will be created. Migration Requirements To be eligible for migration, the active eBay listings must meet the following requirements: Listing type is Fixed-Price Note: Auction listings are supported by the Inventory API, but the bulkMigrateListing method cannot be used to migrate auction listings. The item(s) in the listings must have seller-defined SKU values associated with them, and in the case of a multiple-variation listing, each product variation must also have its own SKU value Business Polices (Payment, Return Policy, and Shipping) must be used on the listing, as legacy payment, return policy, and shipping fields will not be accepted. With the Payment Policy associated with a listing, the immediate payment requirement must be enabled. The postal/zip code ( PostalCode field in Trading's ItemType ) or city ( Location field in Trading's ItemType ) must be set in the listing; the country is also needed, but this value is required in Trading API, so it will always be set for every listing Unsupported Listing Features The following features are not yet available to be set or modified through the Inventory API, but they will remain on the active eBay listing, even after a successful migration to the Inventory model. The downside to this is that the seller will be completely blocked (in APIs or My eBay) from revising these features/settings once the migration takes place: Any listing-level Buyer Requirements Listing enhancements like a bold listing title or Gallery Plus Making the Call In the request payload of the bulkMigrateListings call, the seller will pass in an array of one to five eBay listing IDs (aka Item IDs). To save time and hassle, that seller should do a pre-check on each listing to make sure those listings meet the requirements to be migrated to the new Inventory model. This method also requires the Content-Type request header. See the HTTP request headers for more information. There are no path or query parameters for this call. Call Response If an eBay listing is migrated successfully to the new Inventory model, the following will occur: An Inventory Item object will be created for the item(s) in the listing, and this object will be accessible through the Inventory API An Offer object will be created for the listing, and this object will be accessible through the Inventory API An Inventory Location object will be created and associated with the Offer object, as an Inventory Location must be associated with a published Offer The response payload of the Bulk Migrate Listings call will show the results of each listing migration. These results include an HTTP status code to indicate the success or failure of each listing migration, the SKU value associated with each item, and if the migration is successful, an Offer ID value. The SKU value will be used in the Inventory API to manage the Inventory Item object, and the Offer ID value will be used in the Inventory API to manage the Offer object. Errors and/or warnings containers will be returned for each listing where an error and/or warning occurred with the attempted migration. If a multiple-variation listing is successfully migrated, along with the Offer and Inventory Location objects, an Inventory Item object will be created for each product variation within the listing, and an Inventory Item Group object will also be created, grouping those 

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<MigrateListing> | No | This is the base container of the bulkMigrateListings request payload. One to five eBay listings will be included under this container. |
| requests.listingId | string | No | The unique identifier of the eBay listing to migrate to the new Inventory model. In the Trading API, this field is known as the ItemID . Up to five unique eBay listings may be specified here in separate listingId fields. The seller should make sure that each of these listings meet the requirements t |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<MigrateListingResponse> | No | This is the base container of the response payload of the bulkMigrateListings call. The results of each attempted listing migration is captured under this container. |
| responses.errors | array<Error> | No | If one or more errors occur with the attempt to migrate the listing, this container will be returned with detailed information on each error. |
| responses.errors.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| responses.errors.domain | string | No | The name of the domain in which the error or warning occurred. |
| responses.errors.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| responses.errors.inputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific request element(s) most closely associated to the error or warning, if any. |
| responses.errors.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| responses.errors.message | string | No | A description of the condition that caused the error or warning. |
| responses.errors.outputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific response element(s) most closely associated to the error or warning, if any. |
| responses.errors.parameters | array<ErrorParameter> | No | Various warning and error messages return one or more variables that contain contextual information about the error or waring. This is often the field or value that triggered the error or warning. |
| responses.errors.parameters.name | string | No | This type contains the name and value of an input parameter that contributed to a specific error or warning condition. |
| responses.errors.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| responses.errors.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
| responses.inventoryItemGroupKey | string | No | This field will only be returned for a multiple-variation listing that the seller attempted to migrate. Its value is auto-generated by eBay. For a multiple-variation listing that is successfully migrated to the new Inventory model, eBay automatically creates an inventory item group object for the li |
| responses.inventoryItems | array<InventoryItemListing> | No | This container exists of an array of SKU values and offer IDs. For single-variation listings, this will only be one SKU value and one offer ID (if listing was successfully migrated), but multiple SKU values and offer IDs will be returned for multiple-variation listings. |
| responses.inventoryItems.offerId | string | No | Upon a successful migration of a listing, eBay auto-generates this unique identifier, and this offer ID value will be used to retrieve and manage the newly-created offer object. This value will only be generated and returned if the eBay listing is migrated successfully. |
| responses.inventoryItems.sku | string | No | This is the seller-defined SKU value associated with the item(s) in a listing. This same SKU value will be used to retrieve and manage the newly-created inventory item object if the listing migration is successful. This SKU value will get returned even if the migration is not successful. |
| responses.listingId | string | No | The unique identifier of the eBay listing that the seller attempted to migrate. |
| responses.marketplaceId | string | No | This is the unique identifier of the eBay Marketplace where the listing resides. The value fo the eBay US site will be EBAY_US . For implementation help, refer to eBay API documentation |
| responses.statusCode | integer | No | This field is returned for each listing that the seller attempted to migrate. See the HTTP status codes table to see which each status code indicates. |
| responses.warnings | array<Error> | No | If one or more warnings occur with the attempt to migrate the listing, this container will be returned with detailed information on each warning. It is possible that a listing can be successfully migrated even if a warning occurs. |
| responses.warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| responses.warnings.domain | string | No | The name of the domain in which the error or warning occurred. |
| responses.warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| responses.warnings.inputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific request element(s) most closely associated to the error or warning, if any. |
| responses.warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| responses.warnings.message | string | No | A description of the condition that caused the error or warning. |
| responses.warnings.outputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific response element(s) most closely associated to the error or warning, if any. |
| responses.warnings.parameters | array<ErrorParameter> | No | Various warning and error messages return one or more variables that contain contextual information about the error or waring. This is often the field or value that triggered the error or warning. |
| responses.warnings.parameters.name | string | No | This type contains the name and value of an input parameter that contributed to a specific error or warning condition. |
| responses.warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| responses.warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
