---
title: withdrawOffer
category: Inventory_API
api_name: withdrawOffer
method: POST
path: /offer/{offerId}/withdraw
---

**Category:** Inventory_API
**API:** withdrawOffer

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/offer/{offerId}/withdraw

## API Description
This call is used to end a single-variation listing that is associated with the specified offer. This call is used in place of the deleteOffer call if the seller only wants to end the listing associated with the offer but does not want to delete the offer object. With this call, the offer object remains, but it goes into the unpublished state, and will require a publishOffer call to relist the offer. To end a multiple-variation listing that is associated with an inventory item group, the withdrawOfferByInventoryItemGroup method can be used. This call only ends the multiple-variation listing associated with an inventory item group but does not delete the inventory item group object, nor does it delete any of the offers associated with the inventory item group, but instead all of these offers go into the unpublished state.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offerId (path) | string | Yes | This path parameter specifies the unique identifier of the offer that is to be withdrawn. Use the getOffers method to retrieve offer IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| listingId | string | No | The unique identifier of the eBay listing associated with the offer that was withdrawn. This field will not be returned if the eBay listing was not successfully ended. |
| warnings | array<Error> | No | This container will be returned if there were one or more warnings associated with the attempt to withdraw the offer. |
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
