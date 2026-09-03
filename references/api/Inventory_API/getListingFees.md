---
title: getListingFees
category: Inventory_API
api_name: getListingFees
method: POST
path: /offer/get_listing_fees
---

**Category:** Inventory_API
**API:** getListingFees

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/offer/get_listing_fees

## API Description
This call is used to retrieve the expected listing fees for up to 250 unpublished offers. An array of one or more offerId values are passed in under the offers container. In the response payload, all listing fees are grouped by eBay marketplace, and listing fees per offer are not shown. A fees container will be returned for each eBay marketplace where the seller is selling the products associated with the specified offers. Errors will occur if the seller passes in offerIds that represent published offers, so this call should be made before the seller publishes offers with the publishOffer .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offers | array<OfferKeyWithId> | No | This container is used to identify one or more (up to 250) unpublished offers for which expected listing fees will be retrieved. The user passes one or more offerId values (maximum of 250) in to this container to identify the unpublished offers in which to retrieve expected listing fees. This call i |
| offers.offerId | string | No | The unique identifier of an unpublished offer for which expected listing fees will be retrieved. One to 250 offerId values can be passed in to the offers container for one getListingFees call. Use the getOffers method to retrieve offer IDs. Note: Errors will occur if offerId values representing publ |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feeSummaries | array<FeeSummary> | No | This container consists of an array of one or more listing fees that the seller can expect to pay for unpublished offers specified in the call request. Many fee types will get returned even when they are 0.0 . |
| feeSummaries.fees | array<Fee> | No | This container is an array of listing fees that can be expected to be applied to an offer on the specified eBay marketplace ( marketplaceId value). Many fee types will get returned even when they are 0.0 . See the Standard selling fees help page for more information on listing fees. |
| feeSummaries.fees.amount | Amount | No | This dollar value in this container is the actual dollar value of the listing fee type specified in the feeType field. |
| feeSummaries.fees.amount.currency | string | No | A three-digit string value representing the type of currency being used. Both the value and currency fields are required/always returned when expressing prices. See the CurrencyCodeEnum type for the full list of currencies and their corresponding three-digit string values. |
| feeSummaries.fees.amount.value | string | No | A string representation of a dollar value expressed in the currency specified in the currency field. Both the value and currency fields are required/always returned when expressing prices. |
| feeSummaries.fees.feeType | string | No | The value returned in this field indicates the type of listing fee that the seller may incur if one or more unpublished offers (offers are specified in the call request) are published on the marketplace specified in the marketplaceId field. Applicable listing fees will often include things such as I |
| feeSummaries.fees.promotionalDiscount | Amount | No | The dollar value in this container indicates any eBay promotional discount applied toward the listing fee type specified in the feeType field. If there was no discount applied toward the fee, this container is still returned but its value is 0.0 . |
| feeSummaries.fees.promotionalDiscount.currency | string | No | A three-digit string value representing the type of currency being used. Both the value and currency fields are required/always returned when expressing prices. See the CurrencyCodeEnum type for the full list of currencies and their corresponding three-digit string values. |
| feeSummaries.fees.promotionalDiscount.value | string | No | A string representation of a dollar value expressed in the currency specified in the currency field. Both the value and currency fields are required/always returned when expressing prices. |
| feeSummaries.marketplaceId | string | No | This is the unique identifier of the eBay site for which listing fees for the offer are applicable. For implementation help, refer to eBay API documentation |
| feeSummaries.warnings | array<Error> | No | This container will contain an array of errors and/or warnings when a call is made, and errors and/or warnings occur. |
| feeSummaries.warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| feeSummaries.warnings.domain | string | No | The name of the domain in which the error or warning occurred. |
| feeSummaries.warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| feeSummaries.warnings.inputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific request element(s) most closely associated to the error or warning, if any. |
| feeSummaries.warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| feeSummaries.warnings.message | string | No | A description of the condition that caused the error or warning. |
| feeSummaries.warnings.outputRefIds | array<string> | No | An array of one or more reference IDs which identify the specific response element(s) most closely associated to the error or warning, if any. |
| feeSummaries.warnings.parameters | array<ErrorParameter> | No | Various warning and error messages return one or more variables that contain contextual information about the error or waring. This is often the field or value that triggered the error or warning. |
| feeSummaries.warnings.parameters.name | string | No | This type contains the name and value of an input parameter that contributed to a specific error or warning condition. |
| feeSummaries.warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| feeSummaries.warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
