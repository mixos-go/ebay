---
title: Creates_promotional_shipping_rules_such_as_discounts_or_free-shipping_thresholds
category: Account_v2_API
api_name: Creates_promotional_shipping_rules_such_as_discounts_or_free-shipping_thresholds
method: POST
path: /combined_shipping_rules/create_promotional_shipping_rule
---

**Category:** Account_v2_API
**API:** Creates_promotional_shipping_rules_such_as_discounts_or_free-shipping_thresholds

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules/create_promotional_shipping_rule

## API Description
Creates promotional shipping rules, such as discounts or free-shipping thresholds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedDuration | CombinedPaymentPeriodEnum | No | This container specifies the time window during which multiple unpaid orders can be combined into a single payment or invoice, represented by using one of the values in CombinedPaymentPeriodEnum . |
| promotionalShippingRule | PromotionalShippingRuleType | Yes | This container defines the promotional combined-shipping rule that offers discounts or free shipping based on order value, item count, or other qualifying conditions. |
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
