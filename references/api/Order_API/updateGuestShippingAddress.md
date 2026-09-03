---
title: updateGuestShippingAddress
category: Order_API
api_name: updateGuestShippingAddress
method: POST
path: /guest_checkout_session/{checkoutSessionId}/update_shipping_address
---

**Category:** Order_API
**API:** updateGuestShippingAddress

**Method:** POST
**HTTP Path:** https://apix.ebay.com{basePath}/guest_checkout_session/{checkoutSessionId}/update_shipping_address

## API Description
Note: The Order API (v2) currently only supports the guest payment/checkout flow. If you need to support member payment/checkout flow, use the v1_beta version of the Order API. Important! (Limited Release) This method is only available to select developers approved by business units. This method changes the shipping address for the order in an eBay guest checkout session. All the line items in an order must be shipped to the same address, but the shipping method can be specific to the line item. Note: If the address submitted cannot be validated, a warning message will be returned. This does not prevent the method from executing, but you may want to verify the address. For a list of supported sites and other restrictions, see API Restrictions in the Order API overview.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| checkoutSessionId (path) | string | Yes | This path parameter specifies the unique eBay-assigned session identifier for a specific eBay marketplace. This value is returned by the initiateGuestCheckoutSession method. Note: When using this ID, the X-EBAY-C-MARKETPLACE-ID value and developer App ID must be the same as that used when this guest |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the eBay marketplace where the order will occur. Note: For this method, this value must match the X-EBAY-C-MARKETPLACE-ID used when the associated checkout session was created. See HTTP request headers for the marketplace ID values. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is used to specify the deviceId for the device/user attempting to make the call. It contains an alphanumeric string that allows a payment gateway to track an API call attempt and confirm that it is a verified payment attempt by a device/user. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| addressLine1 | string | No | The first line of the street address where the item is being shipped. Maximum: 40 characters for AU, CA, and US marketplaces 35 characters for DE and GB marketplaces 50 characters for all other marketplaces |
| addressLine2 | string | No | The second line of the street address where the item is being shipped. This optional field can be used for information such as 'Suite Number' or 'Apt Number'. Maximum: 40 characters for AU, CA, and US marketplaces 35 characters for DE and GB marketplaces 50 characters for all other marketplaces |
| city | string | No | The city of the address where the item is being shipped. |
| country | string | No | The two letter code representing the country of the address. For implementation help, refer to eBay API documentation |
| county | string | No | The county of the address where the item is being shipped. |
| phoneNumber | string | No | The phone number of the person receiving the package. Note: It is highly recommended that when entering the phone number you include the country code. For example, if a US phone number is 4********4 , you would enter +14********4 . If you do not include this code, the service will use the country sp |
| postalCode | string | No | The postal code of the address where the item is being shipped. Note: This is optional when shipping to EBAY_HK (Hong Kong). |
| recipient | Recipient | No | The name of the person receiving the package. |
| recipient.firstName | string | No | The first name of the person receiving the purchase order. |
| recipient.lastName | string | No | The last name of the person receiving the purchase order. |
| stateOrProvince | string | No | The state or province of the address. Note: For the US marketplace, this is a two-character value. For a list of valid values, see US State and Canada Province Codes . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| appliedCoupons | array<Coupon> | No | A container that returns the information for the coupons that were applied in the guest checkout session. |
| appliedCoupons.redemptionCode | string | No | The coupon redemption code. |
| checkoutSessionId | string | No | The eBay-assigned guest checkout session ID. This ID is created after a successful initiateGuestCheckoutSession call. |
| lineItems | array<LineItem> | No | An array of line items associated with the guest checkout session. |
| lineItems.addonServices | array<CheckoutAddonService> | No | An array of add-on services for the line item. |
| lineItems.addonServices.selected | boolean | No | This boolean indicates whether the service is selected or not. |
| lineItems.addonServices.serviceFee | Amount | No | The container that returns the amount and currency of the fee for an add-on service. |
| lineItems.addonServices.serviceFee.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.addonServices.serviceFee.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.addonServices.serviceId | string | No | The unique identifier of the add-on service. |
| lineItems.addonServices.serviceTax | Amount | No | The container that returns the amount and currency of the sales tax applied against the add-on service fee. This tax is based on the state or territory in which the buyer is located. |
| lineItems.addonServices.serviceTax.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.addonServices.serviceTax.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.addonServices.serviceType | string | No | The type of add-on service, such as AUTHENTICITY_GUARANTEE . For implementation help, refer to eBay API documentation |
| lineItems.authenticityVerification | AuthenticityVerificationProgram | No | A container returned for orders that are eligible for eBay's Authenticity Guarantee service. The seller ships Authenticity Guarantee service items to the authentication partner instead of the buyer. If the item is successfully authenticated, the authenticator will ship the item to the buyer. |
| lineItems.authenticityVerification.description | string | No | An informational message that applies to the Authenticity Guarantee program. |
| lineItems.authenticityVerification.outcomeReason | string | No | An informational message regarding the authentication outcome of an Authenticity Guarantee verification inspection. Note: This field is conditionally returned when there is information that applies to the Authenticity Guarantee program. |
| lineItems.authenticityVerification.status | string | No | An enumerated value that indicates whether the order line item has passed or failed the Authenticity Guarantee verification inspection, or whether the inspection and/or results are still pending. Note: This field is conditionally returned when the purchase is complete. Valid Values: PENDING PASSED F |
| lineItems.authenticityVerification.termsWebUrl | string | No | The terms and conditions that apply to the Authenticity Guarantee program. |
| lineItems.baseUnitPrice | Amount | No | The cost of a single quantity of the line item. This is the starting point for computing the price during the checkout session. Note: The price includes the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKE |
| lineItems.baseUnitPrice.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.baseUnitPrice.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.fees | array<Fee> | No | A breakdown of the fees applicable to the line item. |
| lineItems.fees.amount | Amount | No | A container for the currency type and monetary amount of the fee associated with the line item. |
| lineItems.fees.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.fees.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.fees.feeType | string | No | The type of fee associated with the line item. For implementation help, refer to eBay API documentation |
| lineItems.image | Image | No | An eBay-assigned URL of the item image. |
| lineItems.image.imageUrl | string | No | The URL for the image. |
| lineItems.itemId | string | No | The eBay identifier of an item. This ID is returned by the Browse and Feed API methods. The ID is in RESTful item ID format. For example: v1\|2**********6\|5**********4 or v1\|1**********9\|0 . For more information about item IDs for RESTful APIs, see Legacy API compatibility . |
| lineItems.lineItemId | string | No | A unique eBay-assigned ID value that identifies a line item in a checkout session. |
| lineItems.netPrice | Amount | No | The total cost for the line item, taking into account the quantity, any seller item discounts, and any coupon that applies. Note: This does not include any shipping discounts, shipping costs, fees, or seller adjustments. |
| lineItems.netPrice.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.netPrice.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.promotions | array<Promotion> | No | An array of promotions applied to the line item. |
| lineItems.promotions.discount | Amount | No | The details regarding the monetary value of the promotional discount. Note: eBay Bucks are not supported. |
| lineItems.promotions.discount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.promotions.discount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.promotions.message | string | No | The text for the promotion title, which describes the promotion. |
| lineItems.promotions.promotionType | string | No | The kind of promotion. Some examples are: SellerDiscountedPromotionalOffer and COUPON . |
| lineItems.quantity | integer | No | The quantity ordered for the line item. |
| lineItems.seller | Seller | No | A container that returns the information about the seller, such as their eBay user name. |
| lineItems.seller.username | string | No | The user name created by the seller for use on eBay. |
| lineItems.shippingOptions | array<ShippingOption> | No | An array of shipping options that are available for the line item. By default, the first one will be selected. Note: The updateGuestShippingOption method can be used to change the shipping option. |
| lineItems.shippingOptions.baseDeliveryCost | Amount | No | The delivery cost using this shipping option, for this line item, before any delivery discounts are applied. Note: The cost includes the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKETPLACE-ID request he |
| lineItems.shippingOptions.baseDeliveryCost.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.shippingOptions.baseDeliveryCost.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.shippingOptions.deliveryDiscount | Amount | No | The monetary value of any delivery discounts. |
| lineItems.shippingOptions.deliveryDiscount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.shippingOptions.deliveryDiscount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.shippingOptions.ebayShipping | boolean | No | This value indicates whether shipping for this order is managed by eBay ( true ) or by the seller ( false ). |
| lineItems.shippingOptions.importCharges | Amount | No | The Global Shipping Program import charges for this line item. |
| lineItems.shippingOptions.importCharges.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.shippingOptions.importCharges.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.shippingOptions.maxEstimatedDeliveryDate | string | No | The end of the date range in which the purchase order is expected to be delivered to the shipping address. |
| lineItems.shippingOptions.minEstimatedDeliveryDate | string | No | The beginning of the date range in which the purchase order is expected to be delivered to the shipping address. |
| lineItems.shippingOptions.selected | boolean | No | A field that indicates whether the shipping method is selected. |
| lineItems.shippingOptions.shippingCarrierCode | string | No | The shipping provider for the line item, such as FedEx or USPS. |
| lineItems.shippingOptions.shippingOptionId | string | No | A unique ID for the selected shipping option/method. |
| lineItems.shippingOptions.shippingServiceCode | string | No | The name of the shipping service code. For example, Priority Mail Express (provided by USPS) or FedEx International Priority (Provided by FedEx). |
| lineItems.taxDetails | array<TaxDetail> | No | A container that returns the tax information for the line item. |
| lineItems.taxDetails.includedInPrice | boolean | No | A field that indicates whether tax was applied for the cost of the item and its shipping. |
| lineItems.taxDetails.taxJurisdiction | TaxJurisdiction | No | A container that returns the tax jurisdiction information. |
| lineItems.taxDetails.taxJurisdiction.region | Region | No | The region of the tax jurisdiction. |
| lineItems.taxDetails.taxJurisdiction.region.regionName | string | No | A localized text string that indicates the name of the region. Taxes are generally charged at the state/province level, or at the country level in the case of VAT tax. |
| lineItems.taxDetails.taxJurisdiction.region.regionType | string | No | An enumeration value that indicates the type of region for the tax jurisdiction. Valid Values: STATE_OR_PROVINCE COUNTRY For implementation help, refer to eBay API documentation |
| lineItems.taxDetails.taxJurisdiction.taxJurisdictionId | string | No | The identifier of the tax jurisdiction. |
| lineItems.taxDetails.taxType | string | No | A field that indicates the type of tax that may be collected for the item. For implementation help, refer to eBay API documentation |
| lineItems.title | string | No | The seller-created title of the item. |
| pricingSummary | ChkPricingSummaryV2 | No | A container that breaks down the costs for the order, including total cost, shipping cost, tax, fees, and any discounts. |
| pricingSummary.additionalSavings | Amount | No | The total amount of the coupon discounts in the purchase order. |
| pricingSummary.additionalSavings.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.additionalSavings.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.adjustment | Adjustment | No | The total amount of any seller adjustments. An adjustment can be a credit or debit. This is used to catch any monetary changes to the order that are not already captured in one of the other fields. |
| pricingSummary.adjustment.amount | Amount | No | The container that returns the amount and currency of an adjustment. |
| pricingSummary.adjustment.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.adjustment.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.adjustment.label | string | No | The text indicating what the adjustment was for. |
| pricingSummary.deliveryCost | Amount | No | The delivery cost for all of the line items, after any delivery discounts are applied. For example, there are four line items, and the delivery cost for each line item is $5. One of the line items qualifies for free delivery. The deliveryCost would be $15, which is the total cost for delivering all  |
| pricingSummary.deliveryCost.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.deliveryCost.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.fee | Amount | No | The total amount of any fees for all the line items in the order, such as a recycling fee. |
| pricingSummary.fee.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.fee.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importCharges | ImportChargesV2 | No | The sum of all Global Shipping Program import charges, for all the line items in the order. |
| pricingSummary.importCharges.amount | Amount | No | The amount of the import charge. |
| pricingSummary.importCharges.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.importCharges.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importCharges.applicableChargeType | string | No | The type of charge to apply to the order, such as import duties. For implementation help, refer to eBay API documentation |
| pricingSummary.importTax | ImportTax | No | The type of import tax applicable to the order, and the total amount of tax for all line items in the order. |
| pricingSummary.importTax.amount | Amount | No | The total amount of import tax for all line items of an order. |
| pricingSummary.importTax.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.importTax.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importTax.importTaxType | string | No | An enumeration value that indicates the type of import tax applicable to the order. Currently, the only applicable import tax is the Goods and Services tax (indicated with GST ). The Goods and Services tax is only applicable to orders for the eBay Australia marketplace. For implementation help, refe |
| pricingSummary.priceDiscount | Amount | No | The total discount amount for all line items in the order. For example, there are four line items in the order. Two of the line items qualify for a Buy 1, Get 1 offer, which is a $6 and a $15 discount. The priceDiscount value returned would be 21, which is the total of the two discounts. Note: Deliv |
| pricingSummary.priceDiscount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.priceDiscount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.priceSubtotal | Amount | No | The total cost for all line items in the order, taking into account the item quantity, but before adding taxes and delivery costs, or applying discounts, fees, and adjustments. Note: The price includes the value-added tax (VAT) and/or Buyer Protection fee for applicable jurisdictions when requested  |
| pricingSummary.priceSubtotal.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.priceSubtotal.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.tax | Amount | No | The total amount of taxes for all line items in the order. |
| pricingSummary.tax.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.tax.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.total | Amount | No | The total cost of the order, which includes: ( priceSubtotal - priceDiscount ) + deliveryCost + tax +/- adjustment + fee + importCharges - additionalSavings . |
| pricingSummary.total.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.total.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| shippingAddress | ShippingAddress | No | A container that returns the address to which the purchase order will be shipped. |
| shippingAddress.addressLine1 | string | No | The first line of the street address where the item is being shipped. Maximum: 40 characters for AU, CA, and US marketplaces 35 characters for DE and GB marketplaces 50 characters for all other marketplaces |
| shippingAddress.addressLine2 | string | No | The second line of the street address where the item is being shipped. This optional field can be used for information such as 'Suite Number' or 'Apt Number'. Maximum: 40 characters for AU, CA, and US marketplaces 35 characters for DE and GB marketplaces 50 characters for all other marketplaces |
| shippingAddress.city | string | No | The city of the address where the item is being shipped. |
| shippingAddress.country | string | No | The two letter code representing the country of the address. For implementation help, refer to eBay API documentation |
| shippingAddress.county | string | No | The county of the address where the item is being shipped. |
| shippingAddress.phoneNumber | string | No | The phone number of the person receiving the package. Note: It is highly recommended that when entering the phone number you include the country code. For example, if a US phone number is 4********4 , you would enter +14********4 . If you do not include this code, the service will use the country sp |
| shippingAddress.postalCode | string | No | The postal code of the address where the item is being shipped. Note: This is optional when shipping to EBAY_HK (Hong Kong). |
| shippingAddress.recipient | Recipient | No | The name of the person receiving the package. |
| shippingAddress.recipient.firstName | string | No | The first name of the person receiving the purchase order. |
| shippingAddress.recipient.lastName | string | No | The last name of the person receiving the purchase order. |
| shippingAddress.stateOrProvince | string | No | The state or province of the address. Note: For the US marketplace, this is a two-character value. For a list of valid values, see US State and Canada Province Codes . |
| warnings | array<Error> | No | An array of errors or warnings that were generated during the method processing. |
| warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| warnings.domain | string | No | The name of the primary system where the error occurred. This is relevant for application errors. |
| warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | An array of reference IDs that identify the specific request elements most closely associated to the error or warning, if any. |
| warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what what must be done to correct the problem. |
| warnings.message | string | No | A description of the condition that caused the error or warning. |
| warnings.outputRefIds | array<string> | No | An array of reference IDs that identify the specific response elements most closely associated to the error or warning, if any. |
| warnings.parameters | array<ErrorParameter> | No | An array of warning and error messages that return one or more variables contextual information about the error or warning. This is often the field or value that triggered the error or warning. |
| warnings.parameters.name | string | No | The name of the input field that caused an issue with the method request. |
| warnings.parameters.value | string | No | The actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
