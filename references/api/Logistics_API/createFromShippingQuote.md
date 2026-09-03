---
title: createFromShippingQuote
category: Logistics_API
api_name: createFromShippingQuote
method: POST
path: /shipment/create_from_shipping_quote
---

**Category:** Logistics_API
**API:** createFromShippingQuote

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/shipment/create_from_shipping_quote

## API Description
This method creates a shipment based on the shippingQuoteId and rateId values supplied in the request. The rate identified by the rateId value specifies the carrier and service for the package shipment, and the rate ID must be contained in the shipping quote identified by the shippingQuoteId value. Call createShippingQuote to retrieve a set of live shipping rates. Note: The Logistics API only supports USPS shipping rates and labels. When you create a shipment, eBay generates a shipping label that you can download and use to ship your package. In a createFromShippingQuote request, sellers can include a list of shipping options they want to add to the base service quoted in the selected rate. The list of available shipping options is specific to each quoted rate and if available, the options are listed in the rate container of the shipping quote. In addition to a configurable return-to location and other details about the shipment, the response to this method includes: The shipping carrier and service to be used for the package shipment A list of selected shipping options, if any The shipment tracking number The total shipping cost (the sum cost of the base shipping service and any added options) When you create a shipment, your billing agreement account is charged the sum of the baseShippingCost and the total cost of any additional shipping options you might have selected. Use the URL returned in labelDownloadURL field, or call downloadLabelFile with the shipmentId value from the response, to download a shipping label for your package. Important! Sellers must set up their payment method before they can use this method to create a shipment and the associated shipping label. Set up a billing agreement Prior to using this method to create a shipment, sellers must first set up their billing agreement. Failure to do so will return Error 90030 Payment could not be completed. The preferred method for sellers to set up their billing agreement is to go to Set up billing agreement and follow the on-screen directions. Alternatively, sellers can do the following: Go to https://www.ebay.com/ship/single/{order_id}, where {order_id} is that of the order for which the label is being printed. When prompted, select PayPal . Verify that Save PayPal for future purchases is selected. Click Set up Payments which will open PayPal in a pop-up window. Log in using PayPal credentials , and then follow the on-screen prompts to set up the billing agreement. Once the agreement has been set up, sellers can leave this page as there is no need to actually print a label.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header parameter specifies the eBay marketplace for the shipment being created. For a list of valid values, refer to the section Marketplace ID Values in the Using eBay RESTful APIs guide. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| additionalOptions | array<AdditionalOption> | No | Supply a list of one or more shipping options that the seller wants to purchase for this shipment. The baseShippingCost field that's associated with the selected shipping rate is the cost of the base service offered in the rate. In addition to the base service, sellers can add additional shipping se |
| additionalOptions.additionalCost | Amount | No | The monetary cost of the additional shipping option identified by the optionType field. |
| additionalOptions.additionalCost.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| additionalOptions.additionalCost.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| additionalOptions.optionType | string | No | The name of a shipping option that can be purchased in addition to the base shipping cost of this rate. The value supplied in this field must match exactly the option name as supplied by the selected rate. |
| labelCustomMessage | string | No | Optional text to be printed on the shipping label if the selected shipping carrier supports custom messages on their labels. |
| labelSize | string | No | The seller's desired label size. Any supplied value is applied only if the shipping carrier supports multiple label sizes, otherwise the carrier's default label size is used. Currently, the only valid value is: 4"x6" |
| rateId | string | No | The unique eBay-assigned identifier of the shipping rate that the seller selected for the shipment. This value is generated by using the createShippingQuote method and is returned in the rates.rateId field. |
| returnTo | Contact | No | The optional return address and contact details for the shipment. The return address is printed on the shipping label. If not specified, the return address defaults to the shipFrom address returned in shipping quote. |
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
| shippingQuoteId | string | No | The unique eBay-assigned identifier of the shipping quote that was generated by the createShippingQuote method. |

## Response
_No documented response fields._
