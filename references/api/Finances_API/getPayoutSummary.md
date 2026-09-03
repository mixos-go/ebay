---
title: getPayoutSummary
category: Finances_API
api_name: getPayoutSummary
method: GET
path: /payout_summary
---

**Category:** Finances_API
**API:** getPayoutSummary

**Method:** GET
**HTTP Path:** https://apiz.ebay.com{basePath}/payout_summary

## API Description
Important! Due to EU &amp; UK Payments regulatory requirements, an additional security verification via Digital Signatures is required for certain API calls that are made on behalf of EU/UK sellers, including all Finances API methods. Please refer to Digital Signatures for APIs to learn more on the impacted APIs and the process to create signatures to be included in the HTTP payload. Note: The Finances API does not support Team Access . Financial information, such as payouts or transactions, is only returned for the user that makes the call. You cannot use any of the methods in this API to return financial information for another user. This method is used to retrieve cumulative values for payouts in a particular state, or all states. The metadata in the response includes total payouts, the total number of monetary transactions (sales, refunds, credits) associated with those payouts, and the total dollar value of all payouts. If the filter query parameter is used to filter by payout status, only one payout status value may be used. If the filter query parameter is not used to filter by a specific payout status, cumulative values for payouts in all states are returned. The user can also use the filter query parameter to specify a date range, and then only payouts that were processed within that date range are considered. Note: getPayoutSummary will only return data on payouts that occurred less than five years in the past.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the seller's eBay marketplace. See HTTP request headers for the marketplace ID values. Note: If a marketplace ID value is not provided, the default value of EBAY_US is used. |
| filter (query) | string | No | The two filter types that can be used here are discussed below. One or both of these filter types can be used. If none of these filters are used, the data returned in the response will reflect all payouts in all states that have occurred within the last five years: payoutDate : consider payouts proc |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| amount | Amount | No | This container shows the total value (and currency type used) of the seller payouts that match the input criteria. This field is not returned if there are no payouts that match the input criteria. |
| amount.convertedFromCurrency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the convertedFromValue field. This value is the pre-conversion currency. This field is only returned if/when currency conversion was applied by eBay. For implementation help, refer to eBay API documentation |
| amount.convertedFromValue | string | No | The monetary amount before any conversion is performed, in the currency specified by the convertedFromCurrency field. This value is the pre-conversion amount. The value field contains the converted amount of this value, in the currency specified by the currency field. This field is only returned if/ |
| amount.convertedToCurrency | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response can only have a value of CNY . The three-letter ISO 4217 code representing the currency of the amount in the convertedToValue field. This field is only returned for payouts to  |
| amount.convertedToValue | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response only returns value in CNY. The monetary value after any conversion is performed, in the currency specified by the convertedToCurrency field. This value is the converted amount. |
| amount.currency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the value field. This field is always returned with any container using Amount type. Default : The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| amount.exchangeRate | string | No | The exchange rate used for the monetary conversion. This field shows the exchange rate used to convert the dollar value in the value field from the dollar value in the convertedFromValue field. For sellers in mainland China, this field shows the exchange rate to convert the dollar value in the value |
| amount.value | string | No | The monetary amount, in the currency specified by the currency field. This field is always returned with any container using Amount type. |
| payoutCount | integer | No | This integer value indicates the total count of payouts to the seller that match the input criteria. This field is always returned, even if there are no payouts that match the input criteria (its value will show 0 ). |
| transactionCount | integer | No | This integer value indicates the total count of monetary transactions (order payments, buyer refunds, and seller credits) associated with the payouts that match the input criteria. This field is always returned, even if there are no payouts that match the input criteria (its value will show 0 ). If  |
