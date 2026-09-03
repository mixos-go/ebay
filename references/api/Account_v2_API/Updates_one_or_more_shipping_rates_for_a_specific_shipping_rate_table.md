---
title: Updates_one_or_more_shipping_rates_for_a_specific_shipping_rate_table
category: Account_v2_API
api_name: Updates_one_or_more_shipping_rates_for_a_specific_shipping_rate_table
method: POST
path: /rate_table/{rate_table_id}/update_shipping_cost
---

**Category:** Account_v2_API
**API:** Updates_one_or_more_shipping_rates_for_a_specific_shipping_rate_table

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/rate_table/{rate_table_id}/update_shipping_cost

## API Description
Updates one or more shipping rates for a specific shipping rate table.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rate_table_id (path) | string | Yes | This path parameter is the unique identifier for the shipping rate table for which shipping costs will be updated. Use the getRateTables method of the Account API v1 to retrieve rate table IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rates | array<RateUpdate> | Yes | An array of rate objects for which shippingCost and/or additionalCost are to be updated. |
| rates.additionalCost | Amount | No | An additional shipping cost added to the base shipping rate (i.e., shippingCost ). This amount applies only to the following rateTableBasis options: WEIGHT : This is a cost per unit weight and is calculated using the weight of the item(s) being shipped. SURCHARGE : This is a flat amount that is adde |
| rates.additionalCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| rates.additionalCost.value | string | No | The monetary amount in the specified currency . |
| rates.rateId | string | No | The identifier for the rate object. Note: This is a string automatically assigned by the system when the rate object is created. It cannot be changed or updated. |
| rates.shippingCost | Amount | No | This is the base shipping rate for an item. This amount applies only to the following rateTableBasis options: ITEM : This is a flat rate shipping cost per item being shipped. WEIGHT : This is a cost per unit weight and is calculated using the weight of the item(s) being shipped. |
| rates.shippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| rates.shippingCost.value | string | No | The monetary amount in the specified currency . |

## Response
_No documented response fields._
