---
title: bulkPublishOffer
category: Inventory_API
api_name: bulkPublishOffer
method: POST
path: /bulk_publish_offer
---

**Category:** Inventory_API
**API:** bulkPublishOffer

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_publish_offer

## API Description
Note: Each listing can be revised up to 250 times in one calendar day. If this revision threshold is reached, the seller will be blocked from revising the item until the next calendar day. This call is used to convert unpublished offers (up to 25) into published offers, or live eBay listings. The unique identifier ( offerId ) of each offer to publish is passed into the request payload. It is possible that some unpublished offers will be successfully created into eBay listings, but others may fail. The response payload will show the results for each offerId value that is passed into the request payload. The errors and warnings containers will be returned for an offer that had one or more issues being published. Important! Publish offer note: Fields may be optional or conditionally required when calling the create or update methods, but become required when publishing the offer to create active listings. For this method, see Offer fields for a list of fields required to publish an offer. For those who prefer to publish one offer per call, the publishOffer method can be used instead. In the case of a multiple-variation listing, the publishOfferByInventoryItemGroup call should be used instead, as this call will convert all unpublished offers associated with an inventory item group into a multiple-variation listing.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<OfferKeyWithId> | No | This container is used to pass in an array of offers to publish. Up to 25 offers can be published with one bulkPublishOffer method. |
| requests.offerId | string | No | The unique identifier of an unpublished offer for which expected listing fees will be retrieved. One to 250 offerId values can be passed in to the offers container for one getListingFees call. Use the getOffers method to retrieve offer IDs. Note: Errors will occur if offerId values representing publ |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<OfferResponseWithListingId> | No | A node is returned under the responses container to indicate the success or failure of each offer that the seller was attempting to publish. |
| responses.errors | array<Error> | No | This container will be returned if there were one or more errors associated with publishing the offer. |
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
| responses.listingId | string | No | The unique identifier of the newly-created eBay listing. This field is only returned if the seller successfully published the offer and created the new eBay listing. |
| responses.offerId | string | No | The unique identifier of the offer that the seller published (or attempted to publish). |
| responses.statusCode | integer | No | The HTTP status code returned in this field indicates the success or failure of publishing the offer specified in the offerId field. See the HTTP status codes table to see which each status code indicates. |
| responses.warnings | array<Error> | No | This container will be returned if there were one or more warnings associated with publishing the offer. |
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
