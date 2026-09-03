---
title: createShippingQuote
category: Logistics_API
api_name: createShippingQuote
method: POST
path: /shipping_quote
---

**Category:** Logistics_API
**API:** createShippingQuote

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/shipping_quote

## API Description
The createShippingQuote method returns a shipping quote that contains a list of live "rates." Each rate represents an offer made by a shipping carrier for a specific service and each offer has a live quote for the base service cost. Rates have a time window in which they are "live," and rates expire when their purchase window ends. If offered by the carrier, rates can include shipping options (and their associated prices), and users can add any offered shipping option to the base service should they desire. Also, depending on the services required, rates can also include pickup and delivery windows. Note: The Logistics API only supports USPS shipping rates and labels. Each rate is for a single package and is based on the following information: The shipping origin The shipping destination The package size (weight and dimensions) Rates are identified by a unique eBay-assigned rateId and rates are based on price points, pickup and delivery time frames, and other user requirements. Because each rate offered must be compliant with the eBay shipping program, all rates reflect eBay-negotiated prices. The various rates returned in a shipping quote offer the user a choice from which they can choose a shipping service that best fits their needs. Select the rate for your shipment and using the associated rateId , call createFromShippingQuote to create a shipment and generate a shipping label that you can use to ship the package.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header parameter specifies the eBay marketplace for the shipping quote that is being created. For a list of valid values, refer to the section Marketplace ID Values in the Using eBay RESTful APIs guide. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| orders | array<Order> | No | In this array, the seller specifies one or more orders that will be shipped in the shipping package. A shipping package can contain any number of line items from one or more orders, providing they all ship in the same package. Maximum list size: 10 |
| orders.channel | string | No | The marketplace where the order was created. Use the value EBAY to get the rates available for eBay orders. |
| orders.orderId | string | No | The unique identifier of the order. The getOrders method of the Fulfillment API can be used to retrieve order IDs. |
| packageSpecification | PackageSpecification | No | Declares the weight and dimensions of the package. |
| packageSpecification.dimensions | Dimensions | No | Declares the height, length, width, and unit of measure for the package to be shipped. |
| packageSpecification.dimensions.height | string | No | The numeric value of the height of the package. |
| packageSpecification.dimensions.length | string | No | The numeric value of the length of the package. |
| packageSpecification.dimensions.unit | string | No | The unit of measure used to express the height, length, and width of the package. For implementation help, refer to eBay API documentation |
| packageSpecification.dimensions.width | string | No | The numeric value of the width of the package. |
| packageSpecification.weight | Weight | No | Declares the weight of the package. |
| packageSpecification.weight.unit | string | No | The unit of measurement used to specify the weight of a shipping package. Both the unit and value fields are required if the weight container is used. If the English system of measurement is being used, the applicable values for weight units are POUND and OUNCE . If the metric system of measurement  |
| packageSpecification.weight.value | string | No | The numeric value of the weight of the package, as measured by the value of unit . |
| shipFrom | Contact | No | The address and contact details pertaining to the origin of the shipment. |
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
| shipTo | Contact | No | The address and contact details pertaining to the shipment's destination. |
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

## Response
_No documented response fields._
