---
title: getReturnPolicies
category: Account_v1_API
api_name: getReturnPolicies
method: GET
path: /return_policy
---

**Category:** Account_v1_API
**API:** getReturnPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/return_policy

## API Description
This method retrieves all the return policies configured for the marketplace you specify using the marketplace_id query parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Language (header) | string | No | Get the correct policies for a marketplace that supports multiple locales using the Content-Language request header. For example, get the policies for the French locale of the Canadian marketplace by specifying fr-CA for the Content-Language header. Likewise, target the Dutch locale of the Belgium m |
| marketplace_id (query) | string | Yes | This query parameter specifies the ID of the eBay marketplace of the policies you want to retrieve. For implementation help, refer to eBay API documentation at https://developer.ebay.com/api-docs/sell/account/types/ba:MarketplaceIdEnum |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | This field is for future use. |
| limit | integer | No | This field is for future use. |
| next | string | No | This field is for future use. |
| offset | integer | No | This field is for future use. |
| prev | string | No | This field is for future use. |
| returnPolicies | array<ReturnPolicy> | No | A list of all of the seller's return business policies defined for the specified marketplace. This array will be returned as empty if no return business policies are defined for the specified marketplace. |
| returnPolicies.categoryTypes | array<CategoryType> | No | This container indicates which category group that the return policy applies to. Note : Return business policies are not applicable to motor vehicle listings, so the categoryTypes.name value will always be ALL_EXCLUDING_MOTORS_VEHICLES for return business policies. |
| returnPolicies.categoryTypes.default | boolean | No | Note: This field has been deprecated and is no longer used. Do not include this field in any create or update method. This field may be returned within the payload of a get method, but it can be ignored. |
| returnPolicies.categoryTypes.name | string | No | The category type to which the policy applies (motor vehicles or non-motor vehicles). Note: The MOTORS_VEHICLES category type is not valid for return policies. eBay flows do not support the return of motor vehicles. For implementation help, refer to eBay API documentation |
| returnPolicies.description | string | No | A seller-defined description of the return business policy. This description is only for the seller's use, and is not exposed on any eBay pages. Max length : 250 |
| returnPolicies.extendedHolidayReturnsOffered | boolean | No | Important! This field is deprecated, since eBay no longer supports extended holiday returns. Any value supplied in this field is neither read nor returned. |
| returnPolicies.internationalOverride | InternationalReturnOverrideType | No | This container shows the seller's international return policy settings. This container is only returned if the seller has set a separate international return policy for the business policy. International return policies are optional, even if the seller ships to international locations. If a separate |
| returnPolicies.internationalOverride.returnMethod | string | No | This field sets/indicates if the seller offers replacement items to the buyer in the case of an international return. The buyer must be willing to accept a replacement item; otherwise, the seller will need to issue a refund for a return. For implementation help, refer to eBay API documentation |
| returnPolicies.internationalOverride.returnPeriod | TimeDuration | No | This container indicates the number of calendar days that the buyer has to return an item. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. You must set the value to one that's accepted by the marketplace and category where the item is listed. M |
| returnPolicies.internationalOverride.returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| returnPolicies.internationalOverride.returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnPolicies.internationalOverride.returnsAccepted | boolean | No | If set to true , the seller accepts international returns. If set to false , the seller does not accept international returns. This field is conditionally required if the seller chooses to have a separate international return policy. |
| returnPolicies.internationalOverride.returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Depending on the return policy and specifics of the return, either the buyer or the seller can be responsible for the return shipping costs. Note that the  |
| returnPolicies.marketplaceId | string | No | The ID of the eBay marketplace to which this return business policy applies. For implementation help, refer to eBay API documentation |
| returnPolicies.name | string | No | A seller-defined name for this return business policy. Names must be unique for policies assigned to the same marketplace. Max length: 64 |
| returnPolicies.refundMethod | string | No | This field indicates the refund method offered by the seller. Its value will be MONEY_BACK unless the seller is enabled for Buy online, Pickup in Store or Click and Collect , and then it might be MERCHANDISE_CREDIT . Getting their money back for returned items is always an option for buyers, regardl |
| returnPolicies.restockingFeePercentage | string | No | Important! This field is deprecated, since eBay no longer allows sellers to charge a restocking fee for buyer remorse returns. If this field is included, it is ignored and it is no longer returned. |
| returnPolicies.returnInstructions | string | No | This text-based field provides more details on seller-specified return instructions. This field is only returned if set for the return business policy. Important! This field is no longer supported on many eBay marketplaces. To see if a marketplace and eBay category does support this field, call getR |
| returnPolicies.returnMethod | string | No | This field is only returned if the seller is willing to offer a replacement item as an alternative to 'Money Back'. For implementation help, refer to eBay API documentation |
| returnPolicies.returnPeriod | TimeDuration | No | This container indicates the number of calendar days that the buyer has to return an item. The return period begins when the item is marked "delivered" at the buyer's specified ship-to location. Most categories support 30-day and 60-day return periods. Note : Unless the seller has set a separate int |
| returnPolicies.returnPeriod.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| returnPolicies.returnPeriod.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnPolicies.returnPolicyId | string | No | A unique eBay-assigned ID for a return business policy. This ID is generated when the policy is created. |
| returnPolicies.returnsAccepted | boolean | No | If this field is returned as true , the seller accepts returns. If set to false , the seller does not accept returns. Note: Top-Rated sellers must accept item returns and the handlingTime should be set to zero days or one day for a listing to receive a Top-Rated Plus badge on the View Item or search |
| returnPolicies.returnShippingCostPayer | string | No | This field indicates who is responsible for paying for the shipping charges for returned items. The field can be set to either BUYER or SELLER . Depending on the return policy and specifics of the return, either the buyer or the seller can be responsible for the return shipping costs. Note that the  |
| total | integer | No | The total number of return business policies retrieved in the result set. If no return business policies are defined for the specified marketplace, this field is returned with a value of 0 . |
