---
title: cancelShipment
category: Logistics_API
api_name: cancelShipment
method: POST
path: /shipment/{shipmentId}/cancel
---

**Category:** Logistics_API
**API:** cancelShipment

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/shipment/{shipmentId}/cancel

## API Description
This method cancels the shipment associated with the specified shipment ID and the associated shipping label is deleted. When you cancel a shipment, the totalShippingCost of the canceled shipment is refunded to the account established by the user's billing agreement. Note that you cannot cancel a shipment if you have used the associated shipping label.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId (path) | string | Yes | This path parameter specifies the unique eBay-assigned ID of the shipment to be canceled. The shipmentId value is generated and returned by the createFromShippingQuote method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| cancellation | ShipmentCancellation | No | Cancellation status for the package, if one exists. |
| cancellation.cancellationRequestedDate | string | No | The time and date the request was made to cancel the shipment, formatted as an ISO 8601 UTC string. |
| cancellation.cancellationStatus | string | No | This enum specifies the current cancellation status of a shipment, if a cancellation request has been made. For implementation help, refer to eBay API documentation |
| creationDate | string | No | The date and time the shipment was created, formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08-20T07:09:00.000Z |
| labelCustomMessage | string | No | If supported by the selected shipping carrier, this field can contain optional seller text to be printed on the shipping label. |
| labelDownloadUrl | string | No | The direct URL the seller can use to download an image of the shipping label. By default, the file format is PDF. See downloadLabelFile for requesting different response file formats. |
| labelSize | string | No | The seller's desired label size. The support for multi-sized labels is shipping-carrier specific and if the size requested in the creaateFromShippingQuote call matches a size the carrier supports, the value will be represented here in the shipment. Currently, the only valid value is: 4"x6" |
| orders | array<Order> | No | A list of one or more orders that will be shipped in the shipping package. |
| orders.channel | string | No | The marketplace where the order was created. Use the value EBAY to get the rates available for eBay orders. |
| orders.orderId | string | No | The unique identifier of the order. The getOrders method of the Fulfillment API can be used to retrieve order IDs. |
| packageSpecification | PackageSpecification | No | The weight and dimensions of the package. |
| packageSpecification.dimensions | Dimensions | No | Declares the height, length, width, and unit of measure for the package to be shipped. |
| packageSpecification.dimensions.height | string | No | The numeric value of the height of the package. |
| packageSpecification.dimensions.length | string | No | The numeric value of the length of the package. |
| packageSpecification.dimensions.unit | string | No | The unit of measure used to express the height, length, and width of the package. For implementation help, refer to eBay API documentation |
| packageSpecification.dimensions.width | string | No | The numeric value of the width of the package. |
| packageSpecification.weight | Weight | No | Declares the weight of the package. |
| packageSpecification.weight.unit | string | No | The unit of measurement used to specify the weight of a shipping package. Both the unit and value fields are required if the weight container is used. If the English system of measurement is being used, the applicable values for weight units are POUND and OUNCE . If the metric system of measurement  |
| packageSpecification.weight.value | string | No | The numeric value of the weight of the package, as measured by the value of unit . |
| rate | PurchasedRate | No | The shipping rate that the seller has chosen to purchase for this shipment. Each rate, identified by a rateId , contains the offered base service, options, and shipping parameters that were selected for the package shipment. |
| rate.additionalOptions | array<AdditionalOption> | No | An list of additional, optional features that have been purchased for the shipment. |
| rate.additionalOptions.additionalCost | Amount | No | The monetary cost of the additional shipping option identified by the optionType field. |
| rate.additionalOptions.additionalCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| rate.additionalOptions.additionalCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| rate.additionalOptions.optionType | string | No | The name of a shipping option that can be purchased in addition to the base shipping cost of this rate. The value supplied in this field must match exactly the option name as supplied by the selected rate. |
| rate.baseShippingCost | Amount | No | The amount of the "base cost" for the shipment as set by the given carrier for the specified service. This cost excludes any addition costs accrued from the addition of any optional shipping options. |
| rate.baseShippingCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| rate.baseShippingCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| rate.destinationTimeZone | string | No | The time zone of the destination according to Time Zone Database . For example, "America/Los_Angeles". |
| rate.maxEstimatedDeliveryDate | string | No | A string value representing maximum (latest) estimated delivery time, formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08-20T07:09:00.000Z |
| rate.minEstimatedDeliveryDate | string | No | A string value representing minimum (earliest) estimated delivery time, formatted as an ISO 8601 ISO 8601 UTC string. |
| rate.pickupNetworks | array<string> | No | A list of pickup networks compatible with the shipping service. |
| rate.pickupSlotId | string | No | This unique eBay-assigned ID value is returned only if the shipment has been configured for a scheduled pickup. |
| rate.pickupType | string | No | The type of pickup or drop off configured for the shipment. For implementation help, refer to eBay API documentation |
| rate.rateId | string | No | The eBay-generated ID of the shipping rate that the seller has chosen to purchase for the shipment. |
| rate.shippingCarrierCode | string | No | The ID code for the carrier that was selected for the package shipment. |
| rate.shippingCarrierName | string | No | The name of the shipping carrier. |
| rate.shippingQuoteId | string | No | The unique eBay-generated ID of the shipping quote from which the seller selected a shipping rate ( rateId ). |
| rate.shippingServiceCode | string | No | String ID code for the shipping service selected for the package shipment. This is a service that the shipping carrier supplies. |
| rate.shippingServiceName | string | No | The name of the shipping service. |
| rate.totalShippingCost | Amount | No | The total shipping cost, which is the sum cost of the base shipping cost and the cost of all the selected shipping options. |
| rate.totalShippingCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| rate.totalShippingCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| returnTo | Contact | No | The address and contact details that should be used for item returns. Sellers have the option to define a return address that is different from their shipFrom address. If not specified, the return address defaults to the shipFrom address in the shipping quote. |
| returnTo.companyName | string | No | The company name with which the contact is associated. |
| returnTo.contactAddress | ContactAddress | No | The details of the contact's geographical address. |
| returnTo.contactAddress.addressLine1 | string | No | The first line of the street address. |
| returnTo.contactAddress.addressLine2 | string | No | The second line of the street address. Use this field for additional address information, such as a suite or apartment number. |
| returnTo.contactAddress.city | string | No | The city in which the address is located. |
| returnTo.contactAddress.countryCode | string | No | The country of the address, represented as two-letter ISO 3166 country code. For example, US represents the United States and DE represents Germany. For implementation help, refer to eBay API documentation |
| returnTo.contactAddress.county | string | No | The county (not country) in which the address is located. Counties typically contain multiple cities or towns. |
| returnTo.contactAddress.postalCode | string | No | The postal code of the address. |
| returnTo.contactAddress.stateOrProvince | string | No | The state or province in which the address is located. States and provinces often contain multiple counties. |
| returnTo.fullName | string | No | The contact's full name. |
| returnTo.primaryPhone | PhoneNumber | No | The contact's primary telephone number. |
| returnTo.primaryPhone.phoneNumber | string | No | A telephone number. |
| shipFrom | Contact | No | The address and contact details for the origin of the package shipment. |
| shipFrom.companyName | string | No | The company name with which the contact is associated. |
| shipFrom.contactAddress | ContactAddress | No | The details of the contact's geographical address. |
| shipFrom.contactAddress.addressLine1 | string | No | The first line of the street address. |
| shipFrom.contactAddress.addressLine2 | string | No | The second line of the street address. Use this field for additional address information, such as a suite or apartment number. |
| shipFrom.contactAddress.city | string | No | The city in which the address is located. |
| shipFrom.contactAddress.countryCode | string | No | The country of the address, represented as two-letter ISO 3166 country code. For example, US represents the United States and DE represents Germany. For implementation help, refer to eBay API documentation |
| shipFrom.contactAddress.county | string | No | The county (not country) in which the address is located. Counties typically contain multiple cities or towns. |
| shipFrom.contactAddress.postalCode | string | No | The postal code of the address. |
| shipFrom.contactAddress.stateOrProvince | string | No | The state or province in which the address is located. States and provinces often contain multiple counties. |
| shipFrom.fullName | string | No | The contact's full name. |
| shipFrom.primaryPhone | PhoneNumber | No | The contact's primary telephone number. |
| shipFrom.primaryPhone.phoneNumber | string | No | A telephone number. |
| shipmentId | string | No | The unique eBay-assigned ID for the shipment. The ID is generated when the shipment is created by a call to createFromShippingQuote . |
| shipmentTrackingNumber | string | No | A unique carrier-assigned ID string that can be used to track the shipment. |
| shipTo | Contact | No | The address and contact details for the destination of the shipment. |
| shipTo.companyName | string | No | The company name with which the contact is associated. |
| shipTo.contactAddress | ContactAddress | No | The details of the contact's geographical address. |
| shipTo.contactAddress.addressLine1 | string | No | The first line of the street address. |
| shipTo.contactAddress.addressLine2 | string | No | The second line of the street address. Use this field for additional address information, such as a suite or apartment number. |
| shipTo.contactAddress.city | string | No | The city in which the address is located. |
| shipTo.contactAddress.countryCode | string | No | The country of the address, represented as two-letter ISO 3166 country code. For example, US represents the United States and DE represents Germany. For implementation help, refer to eBay API documentation |
| shipTo.contactAddress.county | string | No | The county (not country) in which the address is located. Counties typically contain multiple cities or towns. |
| shipTo.contactAddress.postalCode | string | No | The postal code of the address. |
| shipTo.contactAddress.stateOrProvince | string | No | The state or province in which the address is located. States and provinces often contain multiple counties. |
| shipTo.fullName | string | No | The contact's full name. |
| shipTo.primaryPhone | PhoneNumber | No | The contact's primary telephone number. |
| shipTo.primaryPhone.phoneNumber | string | No | A telephone number. |
