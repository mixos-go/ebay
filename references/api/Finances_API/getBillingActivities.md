---
title: getBillingActivities
category: Finances_API
api_name: getBillingActivities
method: GET
path: /billing_activity
---

**Category:** Finances_API
**API:** getBillingActivities

**Method:** GET
**HTTP Path:** https://apiz.ebay.com{basePath}/billing_activity

## API Description
Important! Due to EU &amp; UK Payments regulatory requirements, an additional security verification via Digital Signatures is required for certain API calls that are made on behalf of EU/UK sellers, including all Finances API methods. Please refer to Digital Signatures for APIs to learn more on the impacted APIs and the process to create signatures to be included in the HTTP payload. Note: The Finances API does not support Team Access . Financial information, such as payouts or transactions, is only returned for the user that makes the call. You cannot use any of the methods in this API to return financial information for another user. This method retrieves filtered billing activities of the seller. Returned results are filtered through query parameters such as date range, activity ID, listing ID, or order ID. Sorting and pagination features help organize and navigate returned activities efficiently.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header indicates the natural language and locale preferred by the user for the response. For more information, see the Accept-Language header in HTTP request headers and Marketplace ID values . If not provided, defaults to en-US . |
| filter (query) | string | No | This required field specifies which results to return in the response. Only one of the following four filter values must be used. A user can either retrieve all billing activity within a date range, or they can retrieve billing activity related to a specific eBay order, eBay listing, or they can ret |
| limit (query) | string | No | Sets the maximum number of records to return per page of data. Use this parameter in conjunction with the offset parameter to control the pagination of the output. For example, with offset set to 20 and limit set to 10 , the call retrieves entries 21 through 30 from the result set. Although this fie |
| offset (query) | string | No | Specifies the number of records to skip in the result set. This is used with the limit field to control the pagination of the output. For example: If offset is 0 and limit is 10 , the method will retrieve records 1-10 from the list of records returned If offset is 10 and limit is 10 , the method wil |
| sort (query) | string | No | By default, transactions that match the input criteria are sorted in descending order according to the transaction date (most recent transactions returned first). To view transactions in ascending order instead (oldest transactions first), include the sort query parameter and set its value to sort=t |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| billingActivities | array<BillingActivityLineItem> | No | A list of billing activity entries that meet the filter criteria. Billing activity will include fees, credits, and promotional offers applied to the seller's account. |
| billingActivities.amount | Amount | No | This container shows the amount of the fee or credit. The value and currency are always returned. If the buyer is in one country and purchases from an eBay marketplace that uses a different currency, the response also includes the converted-from and converted-to fields, along with the exchange rate. |
| billingActivities.amount.convertedFromCurrency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the convertedFromValue field. This value is the pre-conversion currency. This field is only returned if/when currency conversion was applied by eBay. For implementation help, refer to eBay API documentation |
| billingActivities.amount.convertedFromValue | string | No | The monetary amount before any conversion is performed, in the currency specified by the convertedFromCurrency field. This value is the pre-conversion amount. The value field contains the converted amount of this value, in the currency specified by the currency field. This field is only returned if/ |
| billingActivities.amount.convertedToCurrency | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response can only have a value of CNY . The three-letter ISO 4217 code representing the currency of the amount in the convertedToValue field. This field is only returned for payouts to  |
| billingActivities.amount.convertedToValue | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response only returns value in CNY. The monetary value after any conversion is performed, in the currency specified by the convertedToCurrency field. This value is the converted amount. |
| billingActivities.amount.currency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the value field. This field is always returned with any container using Amount type. Default : The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| billingActivities.amount.exchangeRate | string | No | The exchange rate used for the monetary conversion. This field shows the exchange rate used to convert the dollar value in the value field from the dollar value in the convertedFromValue field. For sellers in mainland China, this field shows the exchange rate to convert the dollar value in the value |
| billingActivities.amount.value | string | No | The monetary amount, in the currency specified by the currency field. This field is always returned with any container using Amount type. |
| billingActivities.billingTransactionDate | string | No | This timestamp indicates the date/time when eBay processed the transaction. |
| billingActivities.billingTransactionId | string | No | This field provides a unique identifier of the billing transaction. If a seller wants to view details on a specific billing transaction, they can use the actvityId filter and pass in a specific billingTransactionId value. |
| billingActivities.bookingEntry | string | No | The value returned in this field will indicate if the billing transaction is a debit against the seller's account, or a credit. A debit is much more prevalent than a credit, but sometimes a listing fee will get reversed and they will get a credit for this fee. Possible values: DEBIT CREDIT |
| billingActivities.feeType | string | No | This field describes the type of fee associated with the transaction. An example value is FinalValueFeeFixedFeePerOrder . |
| billingActivities.feeTypeDescription | string | No | This field contains the human-readable description of the fee type associated with the transaction. For example, Final Value Fee . |
| billingActivities.listingId | string | No | The unique identifier of the eBay listing associated with the billing transaction. This field is returned if the fee is associated with a listing. |
| billingActivities.orderId | string | No | The unique identifier of the eBay order associated with the billing transaction. This field is returned if the fee is associated with an order. |
| billingActivities.promotionalOffers | array<DiscountDetail> | No | A list of seller promotional offers applicable for the billing transaction. |
| billingActivities.promotionalOffers.amount | Amount | No | This container shows the amount of the promotion. The value and currency are always returned. If the buyer is in one country and purchases from an eBay marketplace that uses a different currency, the response also includes the converted-from and converted-to fields, and the exchange rate. |
| billingActivities.promotionalOffers.amount.convertedFromCurrency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the convertedFromValue field. This value is the pre-conversion currency. This field is only returned if/when currency conversion was applied by eBay. For implementation help, refer to eBay API documentation |
| billingActivities.promotionalOffers.amount.convertedFromValue | string | No | The monetary amount before any conversion is performed, in the currency specified by the convertedFromCurrency field. This value is the pre-conversion amount. The value field contains the converted amount of this value, in the currency specified by the currency field. This field is only returned if/ |
| billingActivities.promotionalOffers.amount.convertedToCurrency | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response can only have a value of CNY . The three-letter ISO 4217 code representing the currency of the amount in the convertedToValue field. This field is only returned for payouts to  |
| billingActivities.promotionalOffers.amount.convertedToValue | string | No | Note: This field is only applicable for Mainland China sellers with an available CNY Bank payment instrument. This response only returns value in CNY. The monetary value after any conversion is performed, in the currency specified by the convertedToCurrency field. This value is the converted amount. |
| billingActivities.promotionalOffers.amount.currency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the value field. This field is always returned with any container using Amount type. Default : The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| billingActivities.promotionalOffers.amount.exchangeRate | string | No | The exchange rate used for the monetary conversion. This field shows the exchange rate used to convert the dollar value in the value field from the dollar value in the convertedFromValue field. For sellers in mainland China, this field shows the exchange rate to convert the dollar value in the value |
| billingActivities.promotionalOffers.amount.value | string | No | The monetary amount, in the currency specified by the currency field. This field is always returned with any container using Amount type. |
| billingActivities.promotionalOffers.offerType | string | No | The type of promotional discount applied through the activity's promotional offer amount . Examples include offer types such as ETRS (eBay Top Rated Seller) and PROMOTION . |
| count | integer | No | An integer representing the number of billing activity items returned in this response page. |
| limit | integer | No | The value of the limit parameter. This is the maximum number of line items, as filtered, of billing transactions to return per page from the result set. |
| next | string | No | The URI for the next page of results starting with the resource name. This URI is returned if there is an additional page of results in the result set. |
| offset | integer | No | The value of the offset parameter. This field indicates how many results were skipped in the response. If an offset parameter was not included in the request, this value will default to 0 , returning the first page of results. |
| prev | string | No | The URI for the previous page of results starting with the resource name. This URI is returned if there is a previous page of results in the result set. |
| total | integer | No | The total number of billing transactions available that match the filter criteria. Note: When the total value exceeds the limit value, there are multiple pages of results. |
