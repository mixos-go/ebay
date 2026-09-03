---
title: Updates_previously_defined_calculated_shipping_rules
category: Account_v2_API
api_name: Updates_previously_defined_calculated_shipping_rules
method: POST
path: /combined_shipping_rules/update_calculated_shipping_rules
---

**Category:** Account_v2_API
**API:** Updates_previously_defined_calculated_shipping_rules

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules/update_calculated_shipping_rules

## API Description
Updates previously defined calculated shipping rules.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| calculatedHandlingRule | CalculatedHandlingRuleType | No | This container specifies the calculated handling rule that determines how handling fees are automatically computed based on order weight, quantity, or value in a combined shipment. |
| calculatedHandlingRule.combinedShippingRuleType | CombinedShippingRuleTypeHandlingEnum | No | This enumeration value specifies the type of combined-shipping rule applied to handling fees (for example, weight-based, flat-rate, or percentage-based calculation method). |
| calculatedHandlingRule.eachAdditionalAmount | Amount | No | This container specifies the additional monetary charge applied for each extra item included in a combined shipment. |
| calculatedHandlingRule.eachAdditionalAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| calculatedHandlingRule.eachAdditionalAmount.value | string | No | The monetary amount in the specified currency . |
| calculatedHandlingRule.eachAdditionalAmountOffShippingCost | Amount | No | This container represents the fixed monetary discount deducted from the total shipping cost for each additional item in a combined shipment. |
| calculatedHandlingRule.eachAdditionalAmountOffShippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| calculatedHandlingRule.eachAdditionalAmountOffShippingCost.value | string | No | The monetary amount in the specified currency . |
| calculatedHandlingRule.eachAdditionalPercentOffShippingCost | number | No | This integer specifies the percentage discount applied to the total shipping cost for each additional item in a combined shipment. |
| calculatedHandlingRule.orderHandlingAmount | Amount | No | This container represents the handling fee charged for processing a combined order, if applicable. |
| calculatedHandlingRule.orderHandlingAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| calculatedHandlingRule.orderHandlingAmount.value | string | No | The monetary amount in the specified currency . |
| calculatedShippingRule | CalculatedShippingRuleType | No | This container defines the calculated shipping rule that determines shipping costs or discounts based on factors such as total weight, price, or item count in a combined order. |
| calculatedShippingRule.combinedShippingRules | array<CombinedShippingRule> | No | This array lists the discount rules applied to combined shipments, detailing calculation methods and rule identifiers. When used by a create call, there won't be any rule ID. |
| calculatedShippingRule.combinedShippingRules.combinedShippingRuleId | string | No | This field represents the unique identifier for the combined-shipping discount profile, used to reference or update a specific rule configuration. |
| calculatedShippingRule.combinedShippingRules.combinedShippingRuleName | string | No | This field specifies the unique name identifying the combined shipping discount profile within the seller’s account. This name is configured by the seller and can have a maximum of XX characters. |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmount | Amount | No | This containter defines the additional monetary charge applied for each extra item when multiple items are shipped together. |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmount.value | string | No | The monetary amount in the specified currency . |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost | Amount | No | This container defines the fixed discount amount deducted from the total shipping cost for each additional item. |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| calculatedShippingRule.combinedShippingRules.eachAdditionalAmountOffShippingCost.value | string | No | The monetary amount in the specified currency . |
| calculatedShippingRule.combinedShippingRules.eachAdditionalPercentOffShippingCost | number | No | This integer specifies the percentage discount applied to the total shipping cost for each additional item in the combined order. |
| calculatedShippingRule.combinedShippingRules.mappedCombinedShippingRuleId | string | No | This field specifies the unique ID that links this combined-shipping rule to another related rule in the seller’s account. |
| calculatedShippingRule.combinedShippingRules.weightOffTotalWeight | MeasureType | No | This container specifies the total weight reduction applied when combining multiple items into one shipment. |
| calculatedShippingRule.combinedShippingRules.weightOffTotalWeight.unit | WeightUnitOfMeasureEnum | No | This field defines the unit of measure (e.g., kilograms, pounds) associated with the value field. |
| calculatedShippingRule.combinedShippingRules.weightOffTotalWeight.value | string | No | This field defines the numeric value representing the measurement, weight, in the specified unit. |
| calculatedShippingRule.combinedShippingRuleType | CombinedShippingRuleTypeEnum | No | This container defines the type of combined-shipping rule applied to calculate discounts, such as weight-based, percentage-based, or flat-rate models. |
| combinedDuration | CombinedPaymentPeriodEnum | No | This enumerated value specifies the duration within which multiple unpaid orders may be combined into a single invoice, represented by one of the values in CombinedPaymentPeriodEnum . |

## Response
_No documented response fields._
