---
title: Updates_existing_flat-rate_shipping_rules
category: Account_v2_API
api_name: Updates_existing_flat-rate_shipping_rules
method: POST
path: /combined_shipping_rules/update_flat_shipping_rules
---

**Category:** Account_v2_API
**API:** Updates_existing_flat-rate_shipping_rules

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules/update_flat_shipping_rules

## API Description
Updates existing flat-rate shipping rules.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedDuration | CombinedPaymentPeriodEnum | Yes | This field specifies the duration within which multiple unpaid orders may be combined into a single invoice. One of the values in CombinedPaymentPeriodEnum must be used in this field. |
| flatShippingRule | FlatShippingRuleType | Yes | This container defines the flat-rate combined-shipping rule, which applies a fixed shipping cost for multiple items shipped together. |
| flatShippingRule.combinedShippingRules | array<CombinedShippingRule> | No | This array specifies the type of combined-shipping rule applied, such as flat-rate or cost-based. |
| flatShippingRule.combinedShippingRules.combinedShippingRuleId | string | No | This field represents the unique identifier for the combined-shipping discount profile, used to reference or update a specific rule configuration. |
| flatShippingRule.combinedShippingRules.combinedShippingRuleName | string | No | This field specifies the unique name identifying the combined shipping discount profile within the seller’s account. This name is configured by the seller and can have a maximum of XX characters. |
| flatShippingRule.combinedShippingRules.eachAdditionalAmount | Amount | No | This containter defines the additional monetary charge applied for each extra item when multiple items are shipped together. |
| flatShippingRule.combinedShippingRules.eachAdditionalAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| flatShippingRule.combinedShippingRules.eachAdditionalAmount.value | string | No | The monetary amount in the specified currency . |
| flatShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost | Amount | No | This container defines the fixed discount amount deducted from the total shipping cost for each additional item. |
| flatShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| flatShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost.value | string | No | The monetary amount in the specified currency . |
| flatShippingRule.combinedShippingRules.eachAdditionalPercentOffShippingCost | number | No | This integer specifies the percentage discount applied to the total shipping cost for each additional item in the combined order. |
| flatShippingRule.combinedShippingRules.mappedCombinedShippingRuleId | string | No | This field specifies the unique ID that links this combined-shipping rule to another related rule in the seller’s account. |
| flatShippingRule.combinedShippingRules.weightOffTotalWeight | MeasureType | No | This container specifies the total weight reduction applied when combining multiple items into one shipment. |
| flatShippingRule.combinedShippingRules.weightOffTotalWeight.unit | WeightUnitOfMeasureEnum | No | This field defines the unit of measure (e.g., kilograms, pounds) associated with the value field. |
| flatShippingRule.combinedShippingRules.weightOffTotalWeight.value | string | No | This field defines the numeric value representing the measurement, weight, in the specified unit. |
| flatShippingRule.combinedShippingRuleType | CombinedShippingRuleTypeEnum | No | This container defines the type of discount rule applied (e.g., percentage-based, fixed-rate). |

## Response
_No documented response fields._
