---
title: Retrieves_all_combined_shipping_rule_configurations_defined_for_the_seller
category: Account_v2_API
api_name: Retrieves_all_combined_shipping_rule_configurations_defined_for_the_seller
method: GET
path: /combined_shipping_rules
---

**Category:** Account_v2_API
**API:** Retrieves_all_combined_shipping_rule_configurations_defined_for_the_seller

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules

## API Description
Retrieves all combined shipping rule configurations defined for the seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| calculatedHandlingRule | CalculatedHandlingRuleType | No | This container will show one or more calculated shipping rules set up for that seller on that ebay marketplace. Note: This will not be returned if a calculated handling rule is not set up for that seller on that eBay marketplace |
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
| calculatedShippingRule | CalculatedShippingRuleType | No | This container specifies the type of combined-shipping rule applied, such as flat-rate, weight-based, or cost-based. |
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
| combinedDuration | CombinedPaymentPeriodEnum | No | This field is represented by one of the values in the CombinedPaymentPeriodEnum . |
| flatShippingRule | FlatShippingRuleType | No | This container will show one or more flat shipping rules set up for that seller on that ebay marketplace. |
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
| promotionalShippingRule | PromotionalShippingRuleType | No | This container shows the promotional shipping rule that is currently set up on the seller's account for the eBay marketplace. This container will not be returned if no promotional shipping rule is currently set up on the seller's account for the eBay marketplace. |
| promotionalShippingRule.combinedShippingRuleType | CombinedShippingRuleTypeEnum | No | This field specifies the type of combined-shipping rule applied, such as flat-rate or cost-based, as defined in the CombinedShippingRuleTypeEnum . |
| promotionalShippingRule.itemCount | integer | No | This integer indicates the quantity of items that must be purchased by the buyer in order for that buyer to qualify for the promotional discount. |
| promotionalShippingRule.orderAmount | Amount | No | This container specifies the minimum order amount required to qualify for the associated discount or promotional rule. |
| promotionalShippingRule.orderAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| promotionalShippingRule.orderAmount.value | string | No | The monetary amount in the specified currency . |
| promotionalShippingRule.shippingCost | Amount | No | This container represents the total shipping cost or discounted shipping charge for the combined order. |
| promotionalShippingRule.shippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| promotionalShippingRule.shippingCost.value | string | No | The monetary amount in the specified currency . |
