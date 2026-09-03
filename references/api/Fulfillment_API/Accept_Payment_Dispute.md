---
title: Accept_Payment_Dispute
category: Fulfillment_API
api_name: Accept_Payment_Dispute
method: POST
path: /payment_dispute/{payment_dispute_id}/accept
---

**Category:** Fulfillment_API
**API:** Accept_Payment_Dispute

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/accept

## API Description
Accept Payment Dispute

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the payment dispute being accepted. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| returnAddress | ReturnAddress | No | This container is used if the seller wishes to provide a return address to the buyer. This container should be used if the seller is requesting that the buyer return the item. |
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
| revision | integer | No | This integer value indicates the revision number of the payment dispute. This field is required. The current revision number for a payment dispute can be retrieved with the getPaymentDispute method. Each time an action is taken against a payment dispute, this integer value increases by 1. |

## Response
_No documented response fields._
