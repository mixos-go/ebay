---
title: getShippingFulfillments
category: Fulfillment_API
api_name: getShippingFulfillments
method: GET
path: /order/{orderId}/shipping_fulfillment
---

**Category:** Fulfillment_API
**API:** getShippingFulfillments

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/order/{orderId}/shipping_fulfillment

## API Description
Use this call to retrieve the contents of all fulfillments currently defined for a specified order based on the order's unique identifier, orderId . This value is returned in the getOrders call's members.orderId field when you search for orders by creation date or shipment status.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| orderId (path) | string | Yes | This path parameter is used to specify the unique identifier of the order associated with the shipping fulfillments being retrieved. Use the getOrders method to retrieve order IDs. Order ID values are also shown in My eBay/Seller Hub. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| fulfillments | array<ShippingFulfillment> | No | This array contains one or more fulfillments required for the order that was specified in method endpoint. |
| fulfillments.fulfillmentId | string | No | The unique identifier of the fulfillment; for example, 9405509699937003457459 . This eBay-generated value is created with a successful createShippingFulfillment call. |
| fulfillments.lineItems | array<LineItemReference> | No | This array contains a list of one or more line items (and purchased quantity) to which the fulfillment applies. |
| fulfillments.lineItems.lineItemId | string | No | This is the unique identifier of the eBay order line item that is part of the shipping fulfillment. Line item Ids can be found in the lineItems. lineItemId field of the getOrders response. |
| fulfillments.lineItems.quantity | integer | No | This is the number of lineItems associated with the trackingNumber specified by the seller. This must be a whole number greater than zero (0). Default: 1 |
| fulfillments.shipmentTrackingNumber | string | No | The tracking number provided by the shipping carrier for the package shipped in this fulfillment. This field is returned if available. |
| fulfillments.shippedDate | string | No | The date and time that the fulfillment package was shipped. This timestamp is in ISO 8601 format, which uses the 24-hour Universal Coordinated Time (UTC) clock. This field should only be returned if the package has been shipped. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2015-08-04T19:0 |
| fulfillments.shippingCarrierCode | string | No | The eBay code identifying the shipping carrier for this fulfillment. This field is returned if available. Note: The Trading API's ShippingCarrierCodeType enumeration type contains the most current list of eBay shipping carrier codes and the countries served by each carrier. See ShippingCarrierCodeTy |
| total | integer | No | The total number of fulfillments in the specified order. Note: If no fulfillments are found for the order, this field is returned with a value of 0 . |
| warnings | array<Error> | No | This array is only returned if one or more errors or warnings occur with the call request. |
| warnings.category | string | No | The context or source of this error or warning. |
| warnings.domain | string | No | The name of the domain containing the service or application. For example, sell is a domain. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use these values as error code identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | A list of one or more specific request elements (if any) associated with the error or warning. The format of these strings depends on the request payload format. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | An expanded version of the message field. Maximum length: 200 characters |
| warnings.message | string | No | A message about the error or warning which is device agnostic and readable by end users and application developers. It explains what the error or warning is, and how to fix it (in a general sense). If applicable, the value is localized to the end user's requested locale. Maximum length: 50 character |
| warnings.outputRefIds | array<string> | No | A list of one or more specific response elements (if any) associated with the error or warning. The format of these strings depends on the request payload format. For JSON, use JSONPath notation. |
| warnings.parameters | array<ErrorParameter> | No | Contains a list of name-value pairs that provide additional information concerning this error or warning. Each item in the list is an input parameter that contributed to the error or warning condition. |
| warnings.parameters.name | string | No | This is the name of input field that caused an issue with the call request. |
| warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the domain's subsystem or subdivision. For example, fulfillment is a subdomain in the sell domain. |
