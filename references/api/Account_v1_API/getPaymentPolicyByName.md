---
title: getPaymentPolicyByName
category: Account_v1_API
api_name: getPaymentPolicyByName
method: GET
path: /payment_policy/get_by_policy_name
---

**Category:** Account_v1_API
**API:** getPaymentPolicyByName

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payment_policy/get_by_policy_name

## API Description
This method retrieves the details of a specific payment policy. Supply both the policy name and its associated marketplace_id in the request query parameters.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Language (header) | string | No | Get the correct policy for a marketplace that supports multiple locales using the Content-Language request header. For example, get a policy for the French locale of the Canadian marketplace by specifying fr-CA for the Content-Language header. Likewise, target the Dutch locale of the Belgium marketp |
| marketplace_id (query) | string | Yes | This query parameter specifies the eBay marketplace of the policy you want to retrieve. For implementation help, refer to eBay API documentation at https://developer.ebay.com/api-docs/sell/account/types/ba:MarketplaceIdEnum |
| name (query) | string | Yes | This query parameter specifies the seller-defined name of the payment policy you want to retrieve. This value can be retrieved for a payment policy by using the getPaymentPolicies method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTypes | array<CategoryType> | No | This container indicates whether the payment policy applies to motor vehicle listings, or if it applies to non-motor vehicle listings. |
| categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| deposit | Deposit | No | This container is applicable only if the categoryTypes.name field is set to MOTORS_VEHICLES , and is only returned if the seller requires an initial deposit on motor vehicles. The container shows the amount due for the deposit and when it is due (within 1-3 days after commitment to purchase, unless  |
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
| description | string | No | A seller-defined description of the payment policy. This description is only for the seller's use, and is not exposed on any eBay pages. Max length : 250 |
| fullPaymentDueIn | TimeDuration | No | This container applies to motor vehicles listings only and indicates when a final payment for the vehicle is due. This value is always returned if categoryTypes is set to MOTORS_VEHICLES . This container indicates the number of days that a buyer has to make their full payment to the seller and close |
| fullPaymentDueIn.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| fullPaymentDueIn.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| immediatePay | boolean | No | If this field is returned as true , immediate payment is required from the buyer for: A fixed-price item An auction item where the buyer uses the 'Buy it Now' option A deposit for a motor vehicle listing It is possible for the seller to set this field as true in the payment business policy, but it w |
| marketplaceId | string | No | The ID of the eBay marketplace to which the payment business policy applies. For implementation help, refer to eBay API documentation |
| name | string | No | A seller-defined name for this payment policy. Names must be unique for policies assigned to the same marketplace. Max length : 64 |
| paymentInstructions | string | No | Although this field may be returned for some older payment business policies, payment instructions are no longer supported by payment business policies. If this field is returned, it can be ignored and these payment instructions will not appear in any listings that use the corresponding business pol |
| paymentMethods | array<PaymentMethod> | No | This container is returned to show the payment methods that are accepted for the payment business policy. Sellers do not have to specify any electronic payment methods for listings, so this array will often be returned empty unless the payment business policy is intended for motor vehicle listings o |
| paymentMethods.brands | array<string> | No | Note : This array is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including any credit card brands accepted. |
| paymentMethods.paymentMethodType | string | No | This array is only applicable for listings supporting offline payment methods. See the PaymentMethodTypeEnum type for supported offline payment method enum values. If offline payments are enabled for the policy, provide at least one offline payment method. For implementation help, refer to eBay API  |
| paymentMethods.recipientAccountReference | RecipientAccountReference | No | Note : This container is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including PayPal. |
| paymentMethods.recipientAccountReference.referenceId | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. |
| paymentMethods.recipientAccountReference.referenceType | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. For implementation help, refer to eBay API documentation |
| paymentPolicyId | string | No | A unique eBay-assigned ID for a payment business policy. This ID is generated when the policy is created. |
