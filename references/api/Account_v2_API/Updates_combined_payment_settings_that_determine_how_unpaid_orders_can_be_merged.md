---
title: Updates_combined_payment_settings_that_determine_how_unpaid_orders_can_be_merged
category: Account_v2_API
api_name: Updates_combined_payment_settings_that_determine_how_unpaid_orders_can_be_merged
method: POST
path: /combined_shipping_rules/update_combined_payments
---

**Category:** Account_v2_API
**API:** Updates_combined_payment_settings_that_determine_how_unpaid_orders_can_be_merged

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/combined_shipping_rules/update_combined_payments

## API Description
Updates combined payment settings that determine how unpaid orders can be merged.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedDuration | CombinedPaymentPeriodEnum | Yes | This field specifies the duration within which multiple unpaid orders may be combined into a single invoice. One of the values in CombinedPaymentPeriodEnum must be used in this field. |

## Response
_No documented response fields._
