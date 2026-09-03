---
title: getGuestPurchaseOrder
category: Order_API
api_name: getGuestPurchaseOrder
method: GET
path: /guest_purchase_order/{purchaseOrderId}
---

**Category:** Order_API
**API:** getGuestPurchaseOrder

**Method:** GET
**HTTP Path:** https://apix.ebay.com{basePath}/guest_purchase_order/{purchaseOrderId}

## API Description
Note: The Order API (v2) currently only supports the guest payment/checkout flow. If you need to support member payment/checkout flow, use the v1_beta version of the Order API. Important! (Limited Release) This method is only available to select developers approved by business units. This method retrieves the details about a specific guest purchase order. It returns the line items, including purchase order status, dates created and modified, item quantity and listing data, payment and shipping information, and prices, taxes, discounts and credits. The purchaseOrderId is passed in as a URI parameter and is required. Note: The purchaseOrderId value is returned in the call-back URL that is sent through the new eBay pay widget. For more information about eBay managed payments and the new Order API payment flow, see Order API in the Buying Integration Guide. You can use this method to not only get the details of a purchase order, but to check the value of the purchaseOrderPaymentStatus field to determine if the order has been paid for. If the order has been paid for, this field will return PAID . For a list of supported sites and other restrictions, see API Restrictions in the Order API overview.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| purchaseOrderId (path) | string | Yes | This path parameter specifies the unique identifier of a purchase order made by a guest buyer, for which details are to be retrieved. Note: This value is returned in the response URL that is sent through the new eBay pay widget. For more information about eBay managed payments and the new Order API  |
| X-EBAY-C-MARKETPLACE-ID (header) | string | No | This header identifies the eBay marketplace where the order will occur. Note: For this method, this value must match the X-EBAY-C-MARKETPLACE-ID used when the associated checkout session was created. See HTTP request headers for the marketplace ID values. |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is used to specify the deviceId for the device/user attempting to make the call. It contains an alphanumeric string that allows a payment gateway to track an API call attempt and confirm that it is a verified payment attempt by a device/user. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| lineItems | array<OrderLineItemV2> | No | An array of line items in the order. |
| lineItems.addonServices | array<AddonService> | No | An array of add-on services that apply to the order line item. |
| lineItems.addonServices.serviceFee | Amount | No | The container that returns the amount and currency of the fee for an add-on service. |
| lineItems.addonServices.serviceFee.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.addonServices.serviceFee.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.addonServices.serviceTax | Amount | No | The container that returns the amount and currency of the sales tax applied against the add-on service fee. This tax is based on the state or territory in which the buyer is located. |
| lineItems.addonServices.serviceTax.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.addonServices.serviceTax.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.addonServices.serviceType | string | No | An enumerated value that defines the type of add-on service. For implementation help, refer to eBay API documentation |
| lineItems.authenticityVerification | AuthenticityVerificationProgram | No | A container that is returned for orders that are eligible for eBay's Authenticity Guarantee program. The seller ships Authenticity Guarantee program items to the authentication partner instead of the buyer. If the item is successfully authenticated, the authenticator will ship the item to the buyer. |
| lineItems.authenticityVerification.description | string | No | An informational message that applies to the Authenticity Guarantee program. |
| lineItems.authenticityVerification.outcomeReason | string | No | An informational message regarding the authentication outcome of an Authenticity Guarantee verification inspection. Note: This field is conditionally returned when there is information that applies to the Authenticity Guarantee program. |
| lineItems.authenticityVerification.status | string | No | An enumerated value that indicates whether the order line item has passed or failed the Authenticity Guarantee verification inspection, or whether the inspection and/or results are still pending. Note: This field is conditionally returned when the purchase is complete. Valid Values: PENDING PASSED F |
| lineItems.authenticityVerification.termsWebUrl | string | No | The terms and conditions that apply to the Authenticity Guarantee program. |
| lineItems.baseUnitPrice | Amount | No | The cost of a single quantity of the line item. Note: The price includes the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKETPLACE-ID request header specifying the supported marketplace (such as EBAY_GB ) |
| lineItems.baseUnitPrice.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.baseUnitPrice.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.fees | array<Fee> | No | A breakdown of the fees applicable to the line item. |
| lineItems.fees.amount | Amount | No | A container for the currency type and monetary amount of the fee associated with the line item. |
| lineItems.fees.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.fees.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.fees.feeType | string | No | The type of fee associated with the line item. For implementation help, refer to eBay API documentation |
| lineItems.image | Image | No | An eBay-assigned URL of the item image. |
| lineItems.image.imageUrl | string | No | The URL for the image. |
| lineItems.itemId | string | No | The eBay identifier of an item. This ID is returned by the Browse and Feed API methods. |
| lineItems.itemOnHold | boolean | No | When this value is true it indicates that the item has been put on hold due to a violation of eBay Policy. |
| lineItems.legacyReference | LegacyReference | No | A container that returns fields to support using the Post Order API for returns and cancellations. For information about what is returned in these fields and how to use the Post Order API, see Using the Post Order API . Note: The Post Order API can be used only with eBay member checkouts. |
| lineItems.legacyReference.legacyItemId | string | No | The legacy ID used to identify an item. This is used by the Post Order API Create Return Request method. This call initiates the item return process. For more information on how to use this field in the Post Order API, see Create a return request in the Buy Integration Guide. Restriction: The Post O |
| lineItems.legacyReference.legacyOrderId | string | No | The legacy ID of the order. This is used by the Post Order API Submit Cancellation Request method. This method initiates the item cancellation process. For more information on how to use this field in the Post Order API, see Using the Post Order API . Restriction: The Post Order API can be used only |
| lineItems.legacyReference.legacyTransactionId | string | No | The legacy ID of the transaction. This is used by the Post Order API Create Return Request call. This call initiates the item return process. For more information on how to use this field in the Post Order API, see Using the Post Order API in the Buy Integration Guide. Restriction: The Post Order AP |
| lineItems.lineItemId | string | No | A unique eBay-assigned ID value that identifies a line item in a checkout session. This is created by the initiateGuestCheckoutSession . |
| lineItems.lineItemPaymentStatus | string | No | An enumeration value that indicates the payment status of the line item. For implementation help, refer to eBay API documentation |
| lineItems.lineItemStatus | string | No | An enumeration value that indicates the fulfillment state of this line item. Note: When there is no tracking information, the status will never change from FULFILLMENT_IN_PROGRESS ; without tracking information, eBay has no way of knowing whether the order was delivered. For implementation help, ref |
| lineItems.netPrice | Amount | No | The total cost for the line item, taking into account the quantity, any seller item discounts, and any coupon that applies. Note: This does not include any shipping discounts, shipping costs, fees, or seller adjustments. |
| lineItems.netPrice.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.netPrice.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.orderId | string | No | The unique order ID for the line item. Maximum Length: 40 characters |
| lineItems.promotions | array<Promotion> | No | An array of promotions applied to the line item. |
| lineItems.promotions.discount | Amount | No | The details regarding the monetary value of the promotional discount. Note: eBay Bucks are not supported. |
| lineItems.promotions.discount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| lineItems.promotions.discount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| lineItems.promotions.message | string | No | The text for the promotion title, which describes the promotion. |
| lineItems.promotions.promotionType | string | No | The kind of promotion. Some examples are: SellerDiscountedPromotionalOffer and COUPON . |
| lineItems.quantity | integer | No | The quantity ordered for the line item. |
| lineItems.seller | Seller | No | A container for information about the seller offering this item, such as the seller's user name. |
| lineItems.seller.username | string | No | The user name created by the seller for use on eBay. |
| lineItems.shippingDetail | ShippingDetail | No | A container for information about the shipping details of the order. |
| lineItems.shippingDetail.ebayShipping | boolean | No | This value indicates whether shipping for this order is managed by eBay ( true ) or by the seller (omitted if false or not applicable to the transaction). When true , the value in the pricingSummary.deliveryCost container indicates the shipping cost paid directly by the buyer to eBay. |
| lineItems.shippingDetail.maxEstimatedDeliveryDate | string | No | The end of the date range in which the purchase order is expected to be delivered to the shipping address (final destination). |
| lineItems.shippingDetail.minEstimatedDeliveryDate | string | No | The beginning of the date range in which the purchase order is expected to be delivered to the shipping address (final destination). |
| lineItems.shippingDetail.shippingCarrierCode | string | No | The shipping provider for the line item, such as FedEx or USPS. |
| lineItems.shippingDetail.shippingServiceCode | string | No | The name of the shipping service option. For example, Priority Mail Express (provided by USPS) or FedEx International Priority (Provided by FedEx). |
| lineItems.taxDetails | array<TaxDetail> | No | A container for the tax information for the line item. Note: The information in this container is only returned when requested from the GB marketplace, when applicable. |
| lineItems.taxDetails.includedInPrice | boolean | No | A field that indicates whether tax was applied for the cost of the item and its shipping. |
| lineItems.taxDetails.taxJurisdiction | TaxJurisdiction | No | A container that returns the tax jurisdiction information. |
| lineItems.taxDetails.taxJurisdiction.region | Region | No | The region of the tax jurisdiction. |
| lineItems.taxDetails.taxJurisdiction.region.regionName | string | No | A localized text string that indicates the name of the region. Taxes are generally charged at the state/province level, or at the country level in the case of VAT tax. |
| lineItems.taxDetails.taxJurisdiction.region.regionType | string | No | An enumeration value that indicates the type of region for the tax jurisdiction. Valid Values: STATE_OR_PROVINCE COUNTRY For implementation help, refer to eBay API documentation |
| lineItems.taxDetails.taxJurisdiction.taxJurisdictionId | string | No | The identifier of the tax jurisdiction. |
| lineItems.taxDetails.taxType | string | No | A field that indicates the type of tax that may be collected for the item. For implementation help, refer to eBay API documentation |
| lineItems.title | string | No | The seller-created title of the item. |
| pricingSummary | ApiPricingSummaryV2 | No | A container that breaks down the costs for the order, including total cost, shipping cost, tax, fees, and any discounts. |
| pricingSummary.additionalSavings | Amount | No | The total amount of the coupon discounts in the purchase order. |
| pricingSummary.additionalSavings.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.additionalSavings.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.addonServicesFee | Amount | No | The total fee for add-on services among all line items. |
| pricingSummary.addonServicesFee.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.addonServicesFee.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.adjustment | Adjustment | No | The total amount of any seller adjustments. An adjustment can be a credit or debit. This is used to catch any monetary changes to the order that are not already captured in one of the other fields. |
| pricingSummary.adjustment.amount | Amount | No | The container that returns the amount and currency of an adjustment. |
| pricingSummary.adjustment.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.adjustment.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.adjustment.label | string | No | The text indicating what the adjustment was for. |
| pricingSummary.deliveryCost | Amount | No | The delivery cost for all of the line items, after any delivery discounts are applied. For example, there are four line items, and the delivery cost for each line item is $5. One of the line items qualifies for free delivery. The deliveryCost would be $15, which is the total cost for delivering all  |
| pricingSummary.deliveryCost.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.deliveryCost.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.deliveryDiscount | Amount | No | The total amount of the order delivery discounts for all of the line items, such as free shipping. |
| pricingSummary.deliveryDiscount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.deliveryDiscount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.fee | Amount | No | The total amount of any fees for all the line items in the order, such as a recycling fee. |
| pricingSummary.fee.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.fee.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importCharges | Amount | No | The sum of all Global Shipping Program import charges, for all the line items in the order. |
| pricingSummary.importCharges.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.importCharges.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importDuties | Amount | No | The total sum of cross-border import duties calculated for all line items in the order, which is paid by the buyer at checkout. |
| pricingSummary.importDuties.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.importDuties.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importTax | ImportTax | No | The type of import tax applicable to the order, and the total amount of tax for all line items in the order. |
| pricingSummary.importTax.amount | Amount | No | The total amount of import tax for all line items of an order. |
| pricingSummary.importTax.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.importTax.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.importTax.importTaxType | string | No | An enumeration value that indicates the type of import tax applicable to the order. Currently, the only applicable import tax is the Goods and Services tax (indicated with GST ). The Goods and Services tax is only applicable to orders for the eBay Australia marketplace. For implementation help, refe |
| pricingSummary.priceDiscount | Amount | No | The total discount amount for all line items in the order. For example, there are four line items in the order. Two of the line items qualify for a Buy 1, Get 1 offer, which is a $6 and a $15 discount. The priceDiscount value returned would be 21, which is the total of the two discounts. Note: Deliv |
| pricingSummary.priceDiscount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.priceDiscount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.priceSubtotal | Amount | No | The total cost for all line items in the order, taking into account the item quantity, but before adding taxes and delivery costs, or applying discounts, fees, and adjustments. Note: The price includes the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. |
| pricingSummary.priceSubtotal.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.priceSubtotal.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.tax | Amount | No | The total amount of taxes for all line items in the order. |
| pricingSummary.tax.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.tax.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| pricingSummary.total | Amount | No | The total cost of the order, which includes: ( priceSubtotal - priceDiscount ) + deliveryCost + tax +/- adjustment + fee + importCharges - additionalSavings . |
| pricingSummary.total.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| pricingSummary.total.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| purchaseOrderCreationDate | string | No | The creation date of the purchase order. |
| purchaseOrderId | string | No | The unique identifier of the purchase order. |
| purchaseOrderPaymentStatus | string | No | A container that returns the payment status for the purchase order. For implementation help, refer to eBay API documentation |
| purchaseOrderStatus | string | No | An enumeration value that indicates the current status of the buyer's payment and any refund that applies to the purchase order. For implementation help, refer to eBay API documentation |
| refundedAmount | Amount | No | The total amount of any refunds for the purchase order. |
| refundedAmount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| refundedAmount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| taxDetails | array<TaxDetails> | No | Detailed tax information for items included in this order. |
| taxDetails.amount | Amount | No | A container for the currency type and monetary amount of the tax item. |
| taxDetails.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| taxDetails.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| taxDetails.taxClassification | string | No | Specifies what the tax item pertains to, such as a tangible object ( ITEM_TAX ), a service ( SERVICE_TAX ), or shipping fees ( SHIPPING_TAX ). For implementation help, refer to eBay API documentation |
| taxDetails.taxClassificationDetails | array<TaxClassificationDetail> | No | Provides a detailed accounting, by TaxType , of taxes collected for each item within an order. |
| taxDetails.taxClassificationDetails.amount | Amount | No | A container for the currency type and monetary amount of the tax collected for an item. |
| taxDetails.taxClassificationDetails.amount.currency | string | No | The currency used in the monetary transaction. Generally, this is the currency used by the country of the eBay site offering the item. For implementation help, refer to eBay API documentation |
| taxDetails.taxClassificationDetails.amount.value | string | No | The amount of the currency specified in the currency field. The value of the currency defaults to the standard currency used by the country of the eBay site offering the item. |
| taxDetails.taxClassificationDetails.taxType | string | No | Indicates the type of tax that has been collected for the item. For implementation help, refer to eBay API documentation |
| warnings | array<Error> | No | A container for any warning messages. |
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
