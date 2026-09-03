---
title: Updates_a_promotional_shipping_rule_to_adjust_discount_thresholds_eligibility_criteria_or_duration_for_the_seller
category: Account_v2_API
api_name: Updates_a_promotional_shipping_rule_to_adjust_discount_thresholds_eligibility_criteria_or_duration_for_the_seller
method: POST
path: /combined_shipping_rules/update_promotional_shipping_rule
---

**Category:** Account_v2_API
**API:** Updates_a_promotional_shipping_rule_to_adjust_discount_thresholds_eligibility_criteria_or_duration_for_the_seller

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules/update_promotional_shipping_rule

## API Description
Updates a promotional shipping rule to adjust discount thresholds, eligibility criteria, or duration for the seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedDuration | CombinedPaymentPeriodEnum | No | This container specifies the duration within which multiple unpaid orders may be combined into a single invoice. One of the values in CombinedPaymentPeriodEnum must be used in this field. |
| promotionalShippingRule | PromotionalShippingRuleType | No | This container specifies the promotional shipping rule that offers discounts or free-shipping options based on defined order thresholds, item counts, or marketplace conditions. |
| promotionalShippingRule.combinedShippingRuleType | CombinedShippingRuleTypeEnum | No | This field specifies the type of combined-shipping rule applied, such as flat-rate or cost-based, as defined in the CombinedShippingRuleTypeEnum . |
| promotionalShippingRule.itemCount | integer | No | This integer indicates the quantity of items that must be purchased by the buyer in order for that buyer to qualify for the promotional discount. |
| promotionalShippingRule.orderAmount | Amount | No | This container specifies the minimum order amount required to qualify for the associated discount or promotional rule. |
| promotionalShippingRule.orderAmount.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| promotionalShippingRule.orderAmount.value | string | No | The monetary amount in the specified currency . |
| promotionalShippingRule.shippingCost | Amount | No | This container represents the total shipping cost or discounted shipping charge for the combined order. |
| promotionalShippingRule.shippingCost.currency | CurrencyCodeEnum | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . |
| promotionalShippingRule.shippingCost.value | string | No | The monetary amount in the specified currency . |

## Response
_No documented response fields._
