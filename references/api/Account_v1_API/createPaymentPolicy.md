---
title: createPaymentPolicy
category: Account_v1_API
api_name: createPaymentPolicy
method: POST
path: /payment_policy
---

**Category:** Account_v1_API
**API:** createPaymentPolicy

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payment_policy

## API Description
This method creates a new payment policy where the policy encapsulates seller's terms for order payments. A successful request returns the getPaymentPolicy URI to the new policy in the Location response header and the ID for the new policy is returned in the response payload. Tip: For details on creating and using the business policies supported by the Account API, see eBay business policies .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTypes | array<CategoryType> | No | This container is used to specify whether the payment business policy applies to motor vehicle listings, or if it applies to non-motor vehicle listings. |
| categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| deposit | Deposit | No | This container is used if the seller wants to require an initial deposit on a motor vehicle listing. In this container, the seller sets the deposit amount and the due date for the deposit. Because eBay controls all electronic payment methods, sellers do not need to specify a payment method and the d |
| deposit.amount | Amount | No | This value indicates the initial deposit amount required from the buyer in order to purchase a motor vehicle. This value can be as high as $2,000.00 if immediate payment is not required, and up to $500.00 if immediate payment is required. Max : 2000.0 |
| deposit.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| deposit.amount.value | string | No | The monetary amount in the specified currency . |
| deposit.dueIn | TimeDuration | No | This value indicates the number of hours that the buyer has (after they commit to buy) to pay the initial deposit on a motor vehicle. Valid dueIn times are 24, 48, and 72 hours. HOUR is set as the unit value, and 24 , 48 or 72 are set in the value field. Note : The dueIn value is overridden if the s |
| deposit.dueIn.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| deposit.dueIn.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| deposit.paymentMethods | array<PaymentMethod> | No | This array is no longer applicable and should not be used since eBay now manages the electronic payment options available to buyers to pay the deposit. |
| deposit.paymentMethods.brands | array<string> | No | Note : This array is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including any credit card brands accepted. |
| deposit.paymentMethods.paymentMethodType | string | No | This array is only applicable for listings supporting offline payment methods. See the PaymentMethodTypeEnum type for supported offline payment method enum values. If offline payments are enabled for the policy, provide at least one offline payment method. For implementation help, refer to eBay API  |
| deposit.paymentMethods.recipientAccountReference | RecipientAccountReference | No | Note : This container is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including PayPal. |
| deposit.paymentMethods.recipientAccountReference.referenceId | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. |
| deposit.paymentMethods.recipientAccountReference.referenceType | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. For implementation help, refer to eBay API documentation |
| description | string | No | A seller-defined description of the payment business policy. This description is only for the seller's use, and is not exposed on any eBay pages. Max length : 250 |
| fullPaymentDueIn | TimeDuration | No | This container is used to specify the number of days that a buyer has to make their full payment to the seller and close the remaining balance on a motor vehicle transaction. This container must be specified for motor vehicles listings. The period starts when the buyer commits to buy. The valid valu |
| fullPaymentDueIn.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| fullPaymentDueIn.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| immediatePay | boolean | No | This field should be included and set to true if the seller wants to require immediate payment from the buyer for: A fixed-price item An auction item where the buyer is using the 'Buy it Now' option A deposit for a motor vehicle listing Default: False |
| marketplaceId | string | No | The ID of the eBay marketplace to which this payment business policy applies. For implementation help, refer to eBay API documentation |
| name | string | No | A seller-defined name for this payment business policy. Names must be unique for policies assigned to the same marketplace. Max length: 64 |
| paymentInstructions | string | No | Note: DO NOT USE THIS FIELD. Payment instructions are no longer supported by payment business policies. A free-form string field that allows sellers to add detailed payment instructions to their listings. |
| paymentMethods | array<PaymentMethod> | No | Note: This field applies only when the seller needs to specify one or more offline payment methods. eBay now manages the electronic payment options available to buyers to pay for the item. This array is used to specify one or more offline payment methods that will be accepted for payment that occurs |
| paymentMethods.brands | array<string> | No | Note : This array is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including any credit card brands accepted. |
| paymentMethods.paymentMethodType | string | No | This array is only applicable for listings supporting offline payment methods. See the PaymentMethodTypeEnum type for supported offline payment method enum values. If offline payments are enabled for the policy, provide at least one offline payment method. For implementation help, refer to eBay API  |
| paymentMethods.recipientAccountReference | RecipientAccountReference | No | Note : This container is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including PayPal. |
| paymentMethods.recipientAccountReference.referenceId | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. |
| paymentMethods.recipientAccountReference.referenceType | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
