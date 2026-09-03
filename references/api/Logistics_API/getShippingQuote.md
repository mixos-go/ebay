---
title: getShippingQuote
category: Logistics_API
api_name: getShippingQuote
method: GET
path: /shipping_quote/{shippingQuoteId}
---

**Category:** Logistics_API
**API:** getShippingQuote

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping_quote/{shippingQuoteId}

## API Description
This method retrieves the complete details of the shipping quote associated with the specified shippingQuoteId value. A "shipping quote" pertains to a single specific package and contains a set of shipping "rates" that quote the cost to ship the package by different shipping carriers and services. The quotes are based on the package's origin, destination, and size. Call createShippingQuote to create a shippingQuoteId .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shippingQuoteId (path) | string | Yes | This path parameter specifies the unique eBay-assigned ID of the shipping quote you want to retrieve. The shippingQuoteId value is generated and returned by the createShippingQuote method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| creationDate | string | No | The date and time this quote was created, expressed as an ISO 8601 UTC string. |
| expirationDate | string | No | The last date and time that this quote will be honored, expressed as an ISO 8601 UTC string. After this time the quote expires and the expressed rates can no longer be purchased. |
| orders | array<Order> | No | A list of one or more orders that will be shipped in the shipping package. |
| orders.channel | string | No | The marketplace where the order was created. Use the value EBAY to get the rates available for eBay orders. |
| orders.orderId | string | No | The unique identifier of the order. The getOrders method of the Fulfillment API can be used to retrieve order IDs. |
| packageSpecification | PackageSpecification | No | The weight and dimensions of the package covered by this shipping quote. |
| packageSpecification.dimensions | Dimensions | No | Declares the height, length, width, and unit of measure for the package to be shipped. |
| packageSpecification.dimensions.height | string | No | The numeric value of the height of the package. |
| packageSpecification.dimensions.length | string | No | The numeric value of the length of the package. |
| packageSpecification.dimensions.unit | string | No | The unit of measure used to express the height, length, and width of the package. For implementation help, refer to eBay API documentation |
| packageSpecification.dimensions.width | string | No | The numeric value of the width of the package. |
| packageSpecification.weight | Weight | No | Declares the weight of the package. |
| packageSpecification.weight.unit | string | No | The unit of measurement used to specify the weight of a shipping package. Both the unit and value fields are required if the weight container is used. If the English system of measurement is being used, the applicable values for weight units are POUND and OUNCE . If the metric system of measurement  |
| packageSpecification.weight.value | string | No | The numeric value of the weight of the package, as measured by the value of unit . |
| rates | array<Rate> | No | A list of rates where each rate, as identified by a rateId , contains information about a specific shipping service offered by a carrier. Rates include shipping carrier and service, the to and from locations, the pickup and delivery windows, the seller's shipping parameters, the service constraints, |
| rates.additionalOptions | array<AdditionalOption> | No | Contains service and pricing information for one or more shipping options that are offered by the carrier and can be purchased in addition to the base shipping service provided by this rate. Shipping options can include items such as INSURANCE and SIGNATURE . |
| rates.additionalOptions.additionalCost | Amount | No | The monetary cost of the additional shipping option identified by the optionType field. |
| rates.additionalOptions.additionalCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| rates.additionalOptions.additionalCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| rates.additionalOptions.optionType | string | No | The name of a shipping option that can be purchased in addition to the base shipping cost of this rate. The value supplied in this field must match exactly the option name as supplied by the selected rate. |
| rates.baseShippingCost | Amount | No | A live quote for the cost that the carrier (identified by shippingCarrierCode ) is charging for the shipping service being offered (identified by shippingServiceCode ), excluding any additional shipping options. |
| rates.baseShippingCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| rates.baseShippingCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| rates.destinationTimeZone | string | No | The name of the time zone region, as defined in the IANA Time Zone Database , to which the package is being shipped. Delivery dates are calculated relative to this time zone. Note: This is different from a Coordinated Universal Time (UTC) offset. For example, the America/Los_Angeles time zone identi |
| rates.maxEstimatedDeliveryDate | string | No | The latest stated date and time the shipment will be delivered at this rate. The time stamp is formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08-20T07:09:00.000Z |
| rates.minEstimatedDeliveryDate | string | No | The estimated earliest date and time the shipment will be delivered at this rate. The time stamp is formatted as an ISO 8601 UTC string. |
| rates.pickupNetworks | array<string> | No | A list of pickup networks compatible with the shipping service. |
| rates.pickupSlots | array<PickupSlot> | No | A list of available pickup slots for the package. |
| rates.pickupSlots.pickupSlotEndTime | string | No | The date and time the pickup slot ends, formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08-20T07:09:00.000Z |
| rates.pickupSlots.pickupSlotId | string | No | Seller-defined name for the pickup slot. |
| rates.pickupSlots.pickupSlotStartTime | string | No | The date and time the pickup slot begins, formatted as an ISO 8601 UTC string. |
| rates.pickupSlots.pickupSlotTimeZone | string | No | The time zone of the pickup location, returned as Time Zone Database ID (also know as an Olson time zone ID). |
| rates.pickupType | string | No | The type of pickup or drop-off service associated with the pickupSlots time frames. For implementation help, refer to eBay API documentation |
| rates.rateId | string | No | The unique eBay-assigned ID for this shipping rate. |
| rates.rateRecommendation | array<string> | No | A list of reasons this rate is recommended. Available values are: BUYER_CHOSEN &mdash; The rate meets or exceeds the requirements of the buyer's preferred shipping option. CHEAPEST_ON_TIME &mdash; The rate is the cheapest rate available that will provide delivery within the seller's time frame commi |
| rates.shippingCarrierCode | string | No | The code name of the shipping carrier who will provide the service identified by shippingServiceCode . |
| rates.shippingCarrierName | string | No | The common name of the shipping carrier. |
| rates.shippingServiceCode | string | No | The code name of the shipping service to be provided by the carrier identified by shippingCarrierCode . |
| rates.shippingServiceName | string | No | The common name of the shipping service. |
| shipFrom | Contact | No | The address and contact details for the origin of the shipment. |
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
| shippingQuoteId | string | No | The unique eBay-assigned ID for this shipping quote. The value of this field is associated with a specific package, based on its origin, destination, and size. |
| shipTo | Contact | No | The address and contact details for the origin of the shipment. |
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
| warnings | array<Error> | No | A list of any warnings triggered by the request. |
| warnings.category | string | No | The category type for this error or warning. It takes a string that can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or request errors fro |
| warnings.domain | string | No | Name of the domain containing the service or application. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| warnings.message | string | No | An end user and app-developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the entity that threw the error. |
| warnings.parameters.value | string | No | A description of the error. |
| warnings.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
