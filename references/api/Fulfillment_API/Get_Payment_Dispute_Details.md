---
title: Get_Payment_Dispute_Details
category: Fulfillment_API
api_name: Get_Payment_Dispute_Details
method: GET
path: /payment_dispute/{payment_dispute_id}
---

**Category:** Fulfillment_API
**API:** Get_Payment_Dispute_Details

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}

## API Description
Get Payment Dispute Details

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the payment dispute being retrieved. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| amount | SimpleAmount | No | This container shows the dollar value associated with the payment dispute in the currency used by the seller's marketplace. |
| amount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| amount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| availableChoices | array<string> | No | The value(s) returned in this array indicate the choices that the seller has when responding to the payment dispute. Once the seller has responded to the payment dispute, this field will no longer be shown, and instead, the sellerResponse field will show the decision that the seller made. |
| buyerProvided | InfoFromBuyer | No | This container is returned if the buyer is returning one or more line items in an order that is associated with the payment dispute, and that buyer has provided return shipping tracking information and/or a note about the return. |
| buyerProvided.contentOnHold | boolean | No | When the value of this field is true it indicates that the buyer's note regarding the payment dispute (i.e., the buyerProvided.note field,) is on hold. When this is the case, the buyerProvided.note field will not be returned. When the value of this field is false , it is not returned. |
| buyerProvided.note | string | No | This field shows any note that was left by the buyer in regard to the dispute. |
| buyerProvided.returnShipmentTracking | array<TrackingInfo> | No | This array shows shipment tracking information for one or more shipping packages being returned to the buyer after a payment dispute. |
| buyerProvided.returnShipmentTracking.shipmentTrackingNumber | string | No | This string value represents the shipment tracking number of the package. |
| buyerProvided.returnShipmentTracking.shippingCarrierCode | string | No | This string value represents the shipping carrier used to ship the package. |
| buyerUsername | string | No | This is the eBay user ID of the buyer that initiated the payment dispute. |
| closedDate | string | No | The timestamp in this field shows the date/time when the payment dispute was closed, so this field is only returned for payment disputes in the CLOSED state. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also k |
| evidence | array<DisputeEvidence> | No | This container shows any evidence that has been provided by the seller to contest the payment dispute. Evidence may include shipment tracking information, proof of authentication documentation, image(s) to proof that an item is as described, or financial documentation/invoice. This container is only |
| evidence.evidenceId | string | No | Unique identifier of the evidential file set. Potentially, each evidential file set can have more than one file, that is why there is this file set identifier, and then an identifier for each file within this file set. |
| evidence.evidenceType | string | No | This enumeration value shows the type of evidential file provided. For implementation help, refer to eBay API documentation |
| evidence.files | array<FileInfo> | No | This array shows the name, ID, file type, and upload date for each provided file. |
| evidence.files.fileId | string | No | The unique identifier of the evidence file. |
| evidence.files.fileType | string | No | The type of file uploaded. Supported file extensions are .JPEG, .JPG, and .PNG., and maximum file size allowed is 1.5 MB. |
| evidence.files.name | string | No | The seller-provided name of the evidence file. |
| evidence.files.uploadedDate | string | No | The timestamp in this field shows the date/time when the seller uploaded the evidential document to eBay. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwich Mean Time (GMT), or Zulu. The ISO- |
| evidence.lineItems | array<OrderLineItems> | No | This array shows one or more order line items associated with the evidential document that has been provided. |
| evidence.lineItems.itemId | string | No | The unique identifier of the eBay listing associated with the order. |
| evidence.lineItems.lineItemId | string | No | The unique identifier of the line item within the order. |
| evidence.providedDate | string | No | The timestamp in this field shows the date/time when the seller provided a requested evidential document to eBay. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwich Mean Time (GMT), or Zulu.  |
| evidence.requestDate | string | No | The timestamp in this field shows the date/time when eBay requested the evidential document from the seller in response to a payment dispute. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwic |
| evidence.respondByDate | string | No | The timestamp in this field shows the date/time when the seller was expected to provide a requested evidential document to eBay. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwich Mean Time ( |
| evidence.shipmentTracking | array<TrackingInfo> | No | This array shows the shipping carrier and shipment tracking number associated with each shipment package of the order. This array is returned under the evidence container if the seller has provided shipment tracking information as evidence to support PROOF_OF_DELIVERY for an INR-related payment disp |
| evidence.shipmentTracking.shipmentTrackingNumber | string | No | This string value represents the shipment tracking number of the package. |
| evidence.shipmentTracking.shippingCarrierCode | string | No | This string value represents the shipping carrier used to ship the package. |
| evidenceRequests | array<EvidenceRequest> | No | This container is returned if one or more evidence documents are being requested from the seller. |
| evidenceRequests.evidenceId | string | No | Unique identifier of the evidential file set. Potentially, each evidential file set can have more than one file, that is why there is this file set identifier, and then an identifier for each file within this file set. |
| evidenceRequests.evidenceType | string | No | This enumeration value shows the type of evidential document provided. For implementation help, refer to eBay API documentation |
| evidenceRequests.lineItems | array<OrderLineItems> | No | This array shows one or more order line items associated with the evidential document that has been provided. |
| evidenceRequests.lineItems.itemId | string | No | The unique identifier of the eBay listing associated with the order. |
| evidenceRequests.lineItems.lineItemId | string | No | The unique identifier of the line item within the order. |
| evidenceRequests.requestDate | string | No | The timestamp in this field shows the date/time when eBay requested the evidential document from the seller in response to a payment dispute. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwic |
| evidenceRequests.respondByDate | string | No | The timestamp in this field shows the date/time when the seller is expected to provide a requested evidential document to eBay. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwich Mean Time (G |
| lineItems | array<OrderLineItems> | No | This array is used to identify one or more order line items associated with the payment dispute. There will always be at least one itemId / lineItemId pair returned in this array. |
| lineItems.itemId | string | No | The unique identifier of the eBay listing associated with the order. |
| lineItems.lineItemId | string | No | The unique identifier of the line item within the order. |
| monetaryTransactions | array<MonetaryTransaction> | No | This array provide details about one or more monetary transactions that occur as part of a payment dispute. This array is only returned once one or more monetary transacations occur with a payment dispute. |
| monetaryTransactions.date | string | No | This timestamp indicates when the monetary transaction occurred. A date is returned for all monetary transactions. The following format is used: YYYY-MM-DDTHH:MM:SS.SSSZ . For example, 2015-08-04T19:09:02.768Z . |
| monetaryTransactions.type | string | No | This enumeration value indicates whether the monetary transaction is a charge or a credit to the seller. For implementation help, refer to eBay API documentation |
| monetaryTransactions.reason | string | No | This enumeration value indicates the reason for the monetary transaction. For implementation help, refer to eBay API documentation |
| monetaryTransactions.amount | DisputeAmount | No | The amount involved in the monetary transaction. For active cross-border trade orders, the currency conversion and exchangeRate fields will be displayed as well. |
| monetaryTransactions.amount.convertedFromCurrency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the convertedFromValue field. This value is the pre-conversion currency. This field is only returned if/when currency conversion was applied by eBay. For implementation help, refer to eBay API documentation |
| monetaryTransactions.amount.convertedFromValue | string | No | The monetary amount before any conversion is performed, in the currency specified by the convertedFromCurrency field. This value is the pre-conversion amount. The value field contains the converted amount of this value, in the currency specified by the currency field. This field is only returned if/ |
| monetaryTransactions.amount.currency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the value field. This field is always returned with any container using Amount type. Default : The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| monetaryTransactions.amount.exchangeRate | string | No | The exchange rate used for the monetary conversion. This field shows the exchange rate used to convert the dollar value in the value field from the dollar value in the convertedFromValue field. This field is only returned if/when currency conversion was applied by eBay. |
| monetaryTransactions.amount.value | string | No | The monetary amount, in the currency specified by the currency field. This field is always returned with any container using Amount type. |
| note | string | No | This field shows information that the seller provides about the dispute, such as the basis for the dispute, any relevant evidence, tracking numbers, and so forth. This field is limited to 1000 characters. |
| openDate | string | No | The timestamp in this field shows the date/time when the payment dispute was opened. This field is returned for payment disputes in all states. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenw |
| orderId | string | No | This is the unique identifier of the order involved in the payment dispute. |
| paymentDisputeId | string | No | This is the unique identifier of the payment dispute. This is the same identifier that is passed in to the call URI. This identifier is automatically created by eBay once the payment dispute comes into the eBay system. |
| paymentDisputeStatus | string | No | The enumeration value in this field gives the current status of the payment dispute. The status of a payment dispute partially determines other fields that are returned in the response. For implementation help, refer to eBay API documentation |
| reason | string | No | The enumeration value in this field gives the reason why the buyer initiated the payment dispute. See DisputeReasonEnum type for a description of the supported reasons that buyers can give for initiating a payment dispute. For implementation help, refer to eBay API documentation |
| resolution | PaymentDisputeOutcomeDetail | No | This container gives details about a payment dispute that has been resolved. This container is only returned for resolved/closed payment disputes. |
| resolution.fees | SimpleAmount | No | This container will show the dollar value of any fees associated with the payment dispute. This container is only returned if there are fees associated with the payment dispute. |
| resolution.fees.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| resolution.fees.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| resolution.protectedAmount | SimpleAmount | No | This container shows the amount of money that the seller is protected against in a payment dispute under eBay's seller protection policy. |
| resolution.protectedAmount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| resolution.protectedAmount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| resolution.protectionStatus | string | No | This enumeration value indicates if the seller is fully protected, partially protected, or not protected by eBay for the payment dispute. This field is always returned once the payment dispute is resolved. For implementation help, refer to eBay API documentation |
| resolution.reasonForClosure | string | No | The enumeration value returned in this field indicates the outcome of the payment dispute for the seller. This field is always returned once the payment dispute is resolved. For implementation help, refer to eBay API documentation |
| resolution.recoupAmount | SimpleAmount | No | This container shows the dollar amount being recouped from the seller. This container is empty if the seller wins the payment dispute or if the seller is fully protected by eBay's seller protection policy. |
| resolution.recoupAmount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| resolution.recoupAmount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| resolution.totalFeeCredit | SimpleAmount | No | This container shows the amount of money in selling fee credits due back to the seller after a payment dispute is settled. |
| resolution.totalFeeCredit.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| resolution.totalFeeCredit.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| respondByDate | string | No | The timestamp in this field shows the date/time when the seller must response to a payment dispute, so this field is only returned for payment disputes in the ACTION_NEEDED state. For payment disputes that currently require action by the seller, that same seller should look at the availableChoices a |
| returnAddress | ReturnAddress | No | This container gives the address where the order will be returned to. This container is returned if the seller is accepting the payment dispute and will issue a refund to the buyer once the item is returned to this address. |
| returnAddress.addressLine1 | string | No | The first line of the street address. |
| returnAddress.addressLine2 | string | No | The second line of the street address. This line is not always necessarily, but is often used for apartment number or suite number, or other relevant information that can not fit on the first line. |
| returnAddress.city | string | No | The city of the return address. |
| returnAddress.country | string | No | The country's two-letter, ISO 3166-1 country code. See the enumeration type for a country's value. For implementation help, refer to eBay API documentation |
| returnAddress.county | string | No | The county of the return address. Counties are not applicable to all countries. |
| returnAddress.fullName | string | No | The full name of return address owner. |
| returnAddress.postalCode | string | No | The postal code of the return address. |
| returnAddress.primaryPhone | Phone | No | This container shows the seller's primary phone number associated with the return address. |
| returnAddress.primaryPhone.countryCode | string | No | The two-letter, ISO 3166 code associated with the seller's phone number. This field is needed if the buyer is located in a different country than the seller. It is also OK to provide if the buyer and seller are both located in the same country See CountryCodeEnum for a list of supported values. |
| returnAddress.primaryPhone.number | string | No | The seller's primary phone number associated with the return address. When this number is provided in a contestPaymentDispute or contestPaymentDispute method, it is provided as one continuous numeric string, including the area code. So, if the phone number's area code was '408', a number in this fie |
| returnAddress.stateOrProvince | string | No | The state or province of the return address. |
| revision | integer | No | This integer value indicates the revision number of the payment dispute. Each time an action is taken against a payment dispute, this integer value increases by 1. |
| sellerResponse | string | No | The enumeration value returned in this field indicates how the seller has responded to the payment dispute. The seller has the option of accepting the payment dispute and agreeing to issue a refund, accepting the payment dispute and agreeing to issue a refund as long as the buyer returns the item, o |
