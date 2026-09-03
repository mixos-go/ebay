---
title: updateReturnPolicy
category: Account_v1_API
api_name: updateReturnPolicy
method: PUT
path: /return_policy/{return_policy_id}
---

**Category:** Account_v1_API
**API:** updateReturnPolicy

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/return_policy/{return_policy_id}

## API Description
This method updates an existing return policy. Specify the policy you want to update using the return_policy_id path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing policy with the new details specified in the payload.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| return_policy_id (path) | string | Yes | This path parameter specifies the ID of the return policy you want to update. This ID can be retrieved for a return policy by using the getReturnPolicies method. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTypes | array<CategoryType> | No | This container indicates which category group that the return policy applies to. Note : Return business policies are not applicable to motor vehicle listings, so the categoryTypes.name value must be set to ALL_EXCLUDING_MOTORS_VEHICLES for return business policies. |
| categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| description | string | No | A seller-defined description of the return business policy. This description is only for the seller's use, and is not exposed on any eBay pages. Max length : 250 |
| extendedHolidayReturnsOffered | boolean | No | Important! This field is deprecated, since eBay no longer supports extended holiday returns. Any value supplied in this field is neither read nor returned. |
| internationalOverride | InternationalReturnOverrideType | No | This container is used by the seller to specify a separate international return policy. If a separate international return policy is not defined by a seller, all of the domestic return policy settings will also apply to international orders. |
| internationalOverride.returnMethod | string | No | This field sets/indicates if the seller offers replacement items to the buyer in the case of an international return. The buyer must be willing to accept a replacement item; otherwise, the seller will need to issue a refund for a return. For implementation help, refer to eBay API documentation |
| internationalOverride.returnPeriod | TimeDuration | No | This container indicates the number of calendar days that the buyer has to return an item. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. You must set the value to one that's accepted by the marketplace and category where the item is listed. M |
| internationalOverride.returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| internationalOverride.returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| internationalOverride.returnsAccepted | boolean | No | If set to true , the seller accepts international returns. If set to false , the seller does not accept international returns. This field is conditionally required if the seller chooses to have a separate international return policy. |
| internationalOverride.returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Depending on the return policy and specifics of the return, either the buyer or the seller can be responsible for the return shipping costs. Note that the  |
| marketplaceId | string | No | The ID of the eBay marketplace to which this return business policy applies. For implementation help, refer to eBay API documentation |
| name | string | No | A seller-defined name for this return business policy. Names must be unique for policies assigned to the same marketplace. Max length : 64 |
| refundMethod | string | No | This field sets the refund method to use for returned items. Its value defaults to MONEY_BACK if omitted, so this field is only needed for Buy online, Pickup in Store or Click and Collect items where the seller is willing to offer merchandise credit as an additional refund method to buyers. Getting  |
| restockingFeePercentage | string | No | Important! This field is deprecated, since eBay no longer allows sellers to charge a restocking fee for buyer remorse returns. If this field is included, it is ignored. |
| returnInstructions | string | No | This text-based field provides more details on seller-specified return instructions. Important! This field is no longer supported on many eBay marketplaces. To see if a marketplace and eBay category does support this field, call getReturnPolicies method of the Metadata API . Then you will look for t |
| returnMethod | string | No | This field can be used if the seller is willing and able to offer a replacement item as an alternative to 'Money Back'. For implementation help, refer to eBay API documentation |
| returnPeriod | TimeDuration | No | This container is used to specify the number of days that the buyer has to return an item. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. You must set the value to one that's accepted by the marketplace and category where the item is listed. M |
| returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnsAccepted | boolean | No | If set to true , the seller accepts returns. If set to false , the seller does not accept returns. Note: Top-Rated sellers must accept item returns and the handlingTime should be set to zero days or one day for a listing to receive a Top-Rated Plus badge on the View Item or search result pages. For  |
| returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Note: Eligible Parts & Accessories (P&A) listings require sellers to offer buyers free returns with a minimum return period of 30 days. See Support for eas |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTypes | array<CategoryType> | No | This field always returns ALL_EXCLUDING_MOTORS_VEHICLES for return business policies, since return business policies are not applicable to motor vehicle listings. |
| categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| description | string | No | A seller-defined description of the return business policy. This description is only for the seller's use, and is not exposed on any eBay pages. This field is returned if set for the policy. Max length : 250 |
| extendedHolidayReturnsOffered | boolean | No | Important! This field is deprecated, since eBay no longer supports extended holiday returns. This field should no longer be returned. |
| internationalOverride | InternationalReturnOverrideType | No | This container is used by the seller to specify a separate international return policy, and will only be returned if the seller has set a separate return policy for international orders. If a separate international return policy is not defined by a seller, all of the domestic return policy settings  |
| internationalOverride.returnMethod | string | No | This field sets/indicates if the seller offers replacement items to the buyer in the case of an international return. The buyer must be willing to accept a replacement item; otherwise, the seller will need to issue a refund for a return. For implementation help, refer to eBay API documentation |
| internationalOverride.returnPeriod | TimeDuration | No | This container indicates the number of calendar days that the buyer has to return an item. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. You must set the value to one that's accepted by the marketplace and category where the item is listed. M |
| internationalOverride.returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| internationalOverride.returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| internationalOverride.returnsAccepted | boolean | No | If set to true , the seller accepts international returns. If set to false , the seller does not accept international returns. This field is conditionally required if the seller chooses to have a separate international return policy. |
| internationalOverride.returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Depending on the return policy and specifics of the return, either the buyer or the seller can be responsible for the return shipping costs. Note that the  |
| marketplaceId | string | No | The ID of the eBay marketplace to which this return business policy applies. For implementation help, refer to eBay API documentation |
| name | string | No | A seller-defined name for this return business policy. Names must be unique for policies assigned to the same marketplace. Max length: 64 |
| refundMethod | string | No | If a seller indicates that they will accept buyer returns, this value will be MONEY_BACK . For implementation help, refer to eBay API documentation |
| restockingFeePercentage | string | No | Important! This field is deprecated, since eBay no longer allows sellers to charge a restocking fee for buyer remorse returns. |
| returnInstructions | string | No | This text-based field provides more details on seller-specified return instructions. Important! This field is no longer supported on many eBay marketplaces. To see if a marketplace and eBay category does support this field, call getReturnPolicies method of the Metadata API . Then you will look for t |
| returnMethod | string | No | This field will be returned if the seller is willing and able to offer a replacement item as an alternative to 'Money Back'. For implementation help, refer to eBay API documentation |
| returnPeriod | TimeDuration | No | This container specifies the amount of days that the buyer has to return the item after receiving it. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. This container will be returned unless the business policy states that the seller does not acc |
| returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnPolicyId | string | No | A unique eBay-assigned ID for a return business policy. This ID is generated when the policy is created. |
| returnsAccepted | boolean | No | If set to true , the seller accepts returns. If set to false , this field indicates that the seller does not accept returns. |
| returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Note: Eligible Parts & Accessories (P&A) listings require sellers to offer buyers free returns with a minimum return period of 30 days. See Support for eas |
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
