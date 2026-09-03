---
title: createReturnPolicy
category: Account_v1_API
api_name: createReturnPolicy
method: POST
path: /return_policy
---

**Category:** Account_v1_API
**API:** createReturnPolicy

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/return_policy

## API Description
This method creates a new return policy where the policy encapsulates seller's terms for returning items. Each policy targets a specific marketplace, and you can create multiple policies for each marketplace. Return policies are not applicable to motor-vehicle listings. A successful request returns the getReturnPolicy URI to the new policy in the Location response header and the ID for the new policy is returned in the response payload. Tip: For details on creating and using the business policies supported by the Account API, see eBay business policies .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
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
_No documented response fields._
