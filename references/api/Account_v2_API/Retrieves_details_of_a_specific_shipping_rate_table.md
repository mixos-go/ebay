---
title: Retrieves_details_of_a_specific_shipping_rate_table
category: Account_v2_API
api_name: Retrieves_details_of_a_specific_shipping_rate_table
method: GET
path: /rate_table/{rate_table_id}
---

**Category:** Account_v2_API
**API:** Retrieves_details_of_a_specific_shipping_rate_table

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/rate_table/{rate_table_id}

## API Description
Retrieves details of a specific shipping rate table.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rate_table_id (path) | string | Yes | This path parameter is the unique identifier for the shipping rate table to retrieve. Use the getRateTables method of the Account API v1 to retrieve rate table IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplaceId | MarketplaceIdEnum | Yes | Identifies the eBay marketplace to which the shipping rate table applies. |
| name | string | Yes | The seller-defined name for the shipping rate table. Names must be unique for each table assigned to the same seller, shippingOptionType, and eBay marketplace. Max length: 50 |
| rates | array<Rate> | Yes | An array of rate objects associated with the specified shipping rate table. Each rate object is identified by a unique system-generated ID and defines specific shipping rate information. |
| rates.additionalCost | Amount | No | An additional shipping cost added to the base shipping rate (i.e., shippingCost ). This amount applies only to the following rateTableBasis options: WEIGHT : This is a cost per unit weight and is calculated using the weight of the item(s) being shipped. SURCHARGE : This is a flat amount that is adde |
| rates.additionalCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| rates.additionalCost.value | string | No | The monetary amount in the specified currency . |
| rates.rateId | string | No | The unique identifier for rate information. Note: This is a string that is automatically assigned by the system when a rate object is created. |
| rates.shippingCategory | ShippingCategoryEnum | No | Indicates the level of shipping service to which the shipping rate information applies. Available shipping categories are: ONE_DAY : This option is not supported when shippingOptionType is INTERNATIONAL. EXPEDITED STANDARD ECONOMY EXPRESS : This option is supported only when MarketplaceId is EBAY_DE |
| rates.shippingCost | Amount | No | Specifies the base shipping rate for an item. This amount applies only to the following rateTableBasis options: ITEM : This is a flat rate shipping cost per item being shipped. WEIGHT : This is a cost per unit weight and is calculated using the weight of the item(s) being shipped. |
| rates.shippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| rates.shippingCost.value | string | No | The monetary amount in the specified currency . |
| rates.shippingRegionNames | array<string> | No | An array of Region names to which the shipping rate information applies. Returned values may be: Geographical Regions (e.g., Worldwide , Europe , and Middle East ) Individual countries identified by a two-letter code such as US (United States), CA (Canada), and GB (United Kingdom) US states and/or C |
| rates.shippingServiceCode | string | No | An enum value that indicates the shipping service used for the specified shipping rate. These enum values align with ShippingService metadata returned by a GeteBayDetails call with DetailName set to shippingServiceDetails . |
| rateTableBasis | ShippingRateCalculationEnum | No | The rate calculation type provides three methods of calculating the shipping cost based on the seller's selection/input: ITEM : Specifies the flat rate shipping cost that buyers in the specified shipping region will pay. When this option is selected, information specified in the rate table overrides |
| rateTableId | string | Yes | A unique, system-generated ID assigned to the shipping rate table when it is initially created. |
| shippingOptionType | ShippingOptionTypeEnum | Yes | The region serviced by the shipping rate table. Valid values are: DOMESTIC : Indicates that the shipping rate table applies to shipping destinations within the country in which an item has been listed (i.e., the source country). INTERNATIONAL : Indicates that the shipping rate table applies to shipp |
