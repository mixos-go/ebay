---
title: updatePaymentPolicy
category: Account_v1_API
api_name: updatePaymentPolicy
method: PUT
path: /payment_policy/{payment_policy_id}
---

**Category:** Account_v1_API
**API:** updatePaymentPolicy

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/payment_policy/{payment_policy_id}

## API Description
This method updates an existing payment policy. Specify the policy you want to update using the payment_policy_id path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing policy with the new details specified in the payload.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_policy_id (path) | string | Yes | This path parameter specifies the ID of the payment policy you want to update. This ID can be retrieved for a payment policy by using the getPaymentPolices method. |
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
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTypes | array<CategoryType> | No | This container indicates whether the payment business policy applies to motor vehicle listings, or if it applies to non-motor vehicle listings. |
| categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| deposit | Deposit | No | This container is only returned if the seller just created or updated a motor vehicles payment business policy and requires buyers to pay an initial deposit after they commit to buying a motor vehicle. |
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
| description | string | No | A seller-defined description of the payment business policy. This description is only for the seller's use, and is not exposed on any eBay pages. This field is returned if set for the policy. Max length : 250 |
| fullPaymentDueIn | TimeDuration | No | The number of days (after the buyer commits to buy) that a buyer has to pay the remaining balance of a motor vehicle transaction. Sellers can set this value to 3, 7, 10, or 14 days. Note: This value is always returned if categoryTypes is set to MOTORS_VEHICLES . |
| fullPaymentDueIn.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| fullPaymentDueIn.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| immediatePay | boolean | No | The value returned in this field will reflect the value set by the seller in the immediatePay request field. A value of true indicates that immediate payment is required from the buyer for: A fixed-price item An auction item where the buyer is using the 'Buy it Now' option A deposit for a motor vehi |
| marketplaceId | string | No | The ID of the eBay marketplace to which this payment business policy applies. For implementation help, refer to eBay API documentation |
| name | string | No | A seller-defined name for this payment business policy. Names must be unique for policies assigned to the same marketplace. Max length: 64 |
| paymentInstructions | string | No | Note: NO LONGER SUPPORTED. Although this field may be returned for some older payment business policies, payment instructions are no longer supported by payment business policies. If this field is returned, it can be ignored and these payment instructions will not appear in any listings that use the |
| paymentMethods | array<PaymentMethod> | No | This array shows the available payment methods that the seller has set for the payment business policy. Sellers do not have to specify any electronic payment methods for listings, so this array will often be returned empty unless the payment business policy is intended for motor vehicle listings or  |
| paymentMethods.brands | array<string> | No | Note : This array is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including any credit card brands accepted. |
| paymentMethods.paymentMethodType | string | No | This array is only applicable for listings supporting offline payment methods. See the PaymentMethodTypeEnum type for supported offline payment method enum values. If offline payments are enabled for the policy, provide at least one offline payment method. For implementation help, refer to eBay API  |
| paymentMethods.recipientAccountReference | RecipientAccountReference | No | Note : This container is no longer applicable and should not be used. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods, including PayPal. |
| paymentMethods.recipientAccountReference.referenceId | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. |
| paymentMethods.recipientAccountReference.referenceType | string | No | Note : DO NOT USE THIS FIELD. eBay now controls all electronic payment methods available for a marketplace, and a seller never has to specify any electronic payment methods. For implementation help, refer to eBay API documentation |
| paymentPolicyId | string | No | A unique eBay-assigned ID for a payment business policy. This ID is generated when the policy is created. |
| warnings | array<Error> | No | An array of one or more errors or warnings that were generated during the processing of the request. If there were no issues with the request, this array will return empty. |
| warnings.category | string | No | The category type for this error or warning. It is a string that can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or request errors from a |
| warnings.domain | string | No | Name of the domain ,or primary system, of the service or application where the error occurred. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | A more detailed explanation of the error than given in the message error field. |
| warnings.message | string | No | Information on how to correct the problem, in the end user's terms and language where applicable. Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional list of name/value pairs that contain context-specific ErrorParameter objects, with each item in the list being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the parameter that caused the error. |
| warnings.parameters.value | string | No | The value of the parameter that caused the error. |
| warnings.subdomain | string | No | If present, indicates the subsystem in which the error occurred. |
