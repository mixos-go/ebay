---
title: publishOffer
category: Inventory_API
api_name: publishOffer
method: POST
path: /offer/{offerId}/publish
---

**Category:** Inventory_API
**API:** publishOffer

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/offer/{offerId}/publish

## API Description
Note: Each listing can be revised up to 250 times in one calendar day. If this revision threshold is reached, the seller will be blocked from revising the item until the next calendar day. This call is used to convert an unpublished offer into a published offer, or live eBay listing. The unique identifier of the offer ( offerId ) is passed in at the end of the call URI. Important! Publish offer note: Fields may be optional or conditionally required when calling the create or update methods, but become required when publishing the offer to create active listings. For this method, see Offer fields for a list of fields required to publish an offer. For those who prefer to publish multiple offers (up to 25 at a time) with one call, the bulkPublishOffer method can be used. In the case of a multiple-variation listing, the publishOfferByInventoryItemGroup call should be used instead, as this call will convert all unpublished offers associated with an inventory item group into a multiple-variation listing.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offerId (path) | string | Yes | This path parameter specifies the unique identifier of the offer that is to be published. Use the getOffers method to retrieve offer IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingId | string | No | The unique identifier of the newly created eBay listing. This field is returned if the single offer (if publishOffer call was used) or group of offers in an inventory item group (if publishOfferByInventoryItemGroup call was used) was successfully converted into an eBay listing. |
| warnings | array<Error> | No | This container will contain an array of errors and/or warnings if any occur when a publishOffer or publishOfferByInventoryItemGroup call is made. |
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
