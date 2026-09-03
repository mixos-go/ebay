---
title: bulkUpdatePriceQuantity
category: Inventory_API
api_name: bulkUpdatePriceQuantity
method: POST
path: /bulk_update_price_quantity
---

**Category:** Inventory_API
**API:** bulkUpdatePriceQuantity

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_update_price_quantity

## API Description
This call is used by the seller to update the total ship-to-home quantity of one inventory item, and/or to update the price and/or quantity of one or more offers associated with one inventory item. Up to 25 offers associated with an inventory item may be updated with one bulkUpdatePriceQuantity call. Only one SKU (one product) can be updated per call. Note: Each listing can be revised up to 250 times in one calendar day. If this revision threshold is reached, the seller will be blocked from revising the item until the next calendar day. Note: In addition to the authorization header, which is required for all Inventory API calls, this call also requires the Content-Type header. See the HTTP request headers for more information. The getOffers call can be used to retrieve all offers associated with a SKU. The seller will just pass in the correct SKU value through the sku query parameter. To update an offer, the offerId value is required, and this value is returned in the getOffers call response. It is also useful to know which offers are unpublished and which ones are published. To get this status, look for the status value in the getOffers call response. Offers in the published state are live eBay listings, and these listings will be revised with a successful bulkUpdatePriceQuantity call. An issue will occur if duplicate offerId values are passed through the same offers container, or if one or more of the specified offers are associated with different products/SKUs. Note: For multiple-variation listings, it is recommended that the bulkUpdatePriceQuantity call be used to update price and quantity information for each SKU within that multiple-variation listing instead of using createOrReplaceInventoryItem calls to update the price and quantity for each SKU. Just remember that only one SKU (one product variation) can be updated per call.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<PriceQuantity> | No | This container is used by the seller to update the total 'ship-to-home' quantity of one or more inventory items (up to 25) and/or to update the price and/or quantity of one or more specific published offers. |
| requests.offers | array<OfferPriceQuantity> | No | This container is needed if the seller is updating the price and/or quantity of one or more published offers, and a successful call will actually update the active eBay listing with the revised price and/or available quantity. This call is not designed to work with unpublished offers. For unpublishe |
| requests.offers.availableQuantity | integer | No | This field is used if the seller wants to modify the current quantity of the inventory item that will be available for purchase in the offer (identified by the corresponding offerId value). This value represents the quantity of the item that is available in the marketplace specified within the offer |
| requests.offers.offerId | string | No | This field is the unique identifier of the offer. If an offers container is used to update one or more offers associated to a specific inventory item, the offerId value is required in order to identify the offer to update with a modified price and/or quantity. The seller can use the getOffers method |
| requests.offers.price | Amount | No | This container is used if the seller wants to modify the current price of the inventory item. The dollar value set here will be the new price of the inventory item in the offer (identified by the corresponding offerId value). Either the availableQuantity field or the price container is required, but |
| requests.offers.price.currency | string | No | A three-digit string value representing the type of currency being used. Both the value and currency fields are required/always returned when expressing prices. See the CurrencyCodeEnum type for the full list of currencies and their corresponding three-digit string values. |
| requests.offers.price.value | string | No | A string representation of a dollar value expressed in the currency specified in the currency field. Both the value and currency fields are required/always returned when expressing prices. |
| requests.shipToLocationAvailability | ShipToLocationAvailability | No | This container is needed if the seller is updating the total 'ship-to-home' quantity for the corresponding inventory item (specified in the sku field). A successful call will update the inventory item record associated with the sku value. |
| requests.shipToLocationAvailability.availabilityDistributions | array<AvailabilityDistribution> | No | This container is used to set the available quantity of the inventory item at one or more warehouse locations. This container will be returned if available quantity is set for one or more inventory locations. |
| requests.shipToLocationAvailability.availabilityDistributions.fulfillmentTime | TimeDuration | No | This container is used to indicate the expected fulfillment time if the inventory item is shipped from the warehouse location identified in the corresponding merchantLocationKey field. The fulfillment time is the estimated number of business days after purchase that the buyer can expect the item to  |
| requests.shipToLocationAvailability.availabilityDistributions.fulfillmentTime.unit | string | No | This enumeration value indicates the time unit used to specify the fulfillment time, such as BUSINESS_DAY . For implementation help, refer to eBay API documentation |
| requests.shipToLocationAvailability.availabilityDistributions.fulfillmentTime.value | integer | No | The integer value in this field, along with the time unit in the unit field, will indicate the fulfillment time. For standard orders that will be shipped, this value will indicate the expected fulfillment time if the inventory item is shipped from the inventory location. If the value of this field i |
| requests.shipToLocationAvailability.availabilityDistributions.merchantLocationKey | string | No | The unique identifier of an inventory location where quantity is available for the inventory item. This field is conditionally required to identify the inventory location that has quantity of the inventory item. Use the getInventoryLocations method to retrieve merchant location keys. |
| requests.shipToLocationAvailability.availabilityDistributions.quantity | integer | No | The integer value passed into this field indicates the quantity of the inventory item that is available at this inventory location. This field is conditionally required. |
| requests.shipToLocationAvailability.quantity | integer | No | This container is used to set the total 'ship-to-home' quantity of the inventory item that will be available for purchase through one or more published offers. This field represents the total quantity of the item that is available for sale across all marketplaces. To update the available quantity al |
| requests.sku | string | No | This is the seller-defined SKU value of the inventory item whose total 'ship-to-home' quantity will be updated. This field is only required when the seller is updating the total quantity of an inventory item using the shipToLocationAvailability container. If the seller is updating the price and/or q |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<PriceQuantityResponse> | No | This container will return an HTTP status code, offer ID, and SKU value for each offer/inventory item being updated, as well as an errors and/or warnings container if any errors or warnings are triggered while trying to update those offers/inventory items. |
| responses.errors | array<Error> | No | This array will be returned if there were one or more errors associated with the update to the offer or inventory item record. |
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
| responses.offerId | string | No | The unique identifier of the offer that was updated. This field will not be returned in situations where the seller is only updating the total 'ship-to-home' quantity of an inventory item record. |
| responses.sku | string | No | This is the seller-defined SKU value of the product. This field is returned whether the seller attempted to update an offer with the SKU value or just attempted to update the total 'ship-to-home' quantity of an inventory item record. Max Length : 50 |
| responses.statusCode | integer | No | The value returned in this container will indicate the status of the attempt to update the price and/or quantity of the offer (specified in the corresponding offerId field) or the attempt to update the total 'ship-to-home' quantity of an inventory item (specified in the corresponding sku field). For |
| responses.warnings | array<Error> | No | This array will be returned if there were one or more warnings associated with the update to the offer or inventory item record. |
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
