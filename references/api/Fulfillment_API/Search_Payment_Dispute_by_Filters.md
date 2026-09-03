---
title: Search_Payment_Dispute_by_Filters
category: Fulfillment_API
api_name: Search_Payment_Dispute_by_Filters
method: GET
path: /payment_dispute_summary
---

**Category:** Fulfillment_API
**API:** Search_Payment_Dispute_by_Filters

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute_summary

## API Description
Search Payment Dispute by Filters

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| order_id (query) | string | No | This filter is used if the seller wishes to retrieve one or more payment disputes filed against a specific order. It is possible that there can be more than one dispute filed against an order if the order has multiple line items. If this filter is used, any other filters are ignored. Use the getOrde |
| buyer_username (query) | string | No | This filter is used if the seller wishes to retrieve one or more payment disputes opened by a specific buyer. The string that is passed in to this query parameter is the eBay user ID of the buyer. |
| open_date_from (query) | string | No | The open_date_from and/or open_date_to date filters are used if the seller wishes to retrieve payment disputes opened within a specific date range. A maximum date range that may be set with the open_date_from and/or open_date_to filters is 90 days. These date filters use the ISO-8601 24-hour date an |
| open_date_to (query) | string | No | The open_date_from and/or open_date_to date filters are used if the seller wishes to retrieve payment disputes opened within a specific date range. A maximum date range that may be set with the open_date_from and/or open_date_to filters is 90 days. These date filters use the ISO-8601 24-hour date an |
| payment_dispute_status (query) | string | No | This filter is used if the seller wishes to only retrieve payment disputes in one or more specific states. To filter by more than one status value, a separate payment_dispute_status filter must be used for each value, as shown below: https://apiz.ebay.com/sell/fulfillment/v1/payment_dispute_summary? |
| limit (query) | string | No | The value passed in this query parameter sets the maximum number of payment disputes to return per page of data. The value passed in this field should be an integer from 1 to 200. If this query parameter is not set, up to 200 records will be returned on each page of results. Min : 1 Max : 200 Defaul |
| offset (query) | string | No | This field is used to specify the number of records to skip in the result set before returning the first payment dispute in the paginated response. A zero-based index is used, so if you set the offset value to 0 (default value), the first payment dispute in the result set appears at the top of the r |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the getPaymentDisputeSummaries call request that produced the current page of the result set. |
| limit | integer | No | This value shows the maximum number of payment disputes that will appear on one page of the result set. The limit value can be passed in as a query parameter in the request, or if it is not used, it defaults to 200 . If the value in the total field exceeds this limit value, there are multiple pages  |
| next | string | No | The getPaymentDisputeSummaries call URI to use if you wish to view the next page of the result set. For example, the following URI returns records 11 thru 20 from the collection of payment disputes: path/payment_dispute_summary?limit=10&offset=10 This field is only returned if there is a next page o |
| offset | integer | No | This integer value indicates the number of payment disputes skipped before listing the first payment dispute from the result set. The offset value can be passed in as a query parameter in the request, or if it is not used, it defaults to 0 and the first payment dispute of the result set is shown at  |
| paymentDisputeSummaries | array<PaymentDisputeSummary> | No | Each payment dispute that matches the input criteria is returned under this array. If no payment disputes are found, an empty array is returned. |
| paymentDisputeSummaries.amount | SimpleAmount | No | This container shows the dollar value associated with the payment dispute in the currency used by the seller's marketplace. This container is returned for all payment disputes returned in the response. |
| paymentDisputeSummaries.amount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| paymentDisputeSummaries.amount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| paymentDisputeSummaries.buyerUsername | string | No | This is the buyer's eBay user ID. This field is returned for all payment disputes returned in the response. |
| paymentDisputeSummaries.closedDate | string | No | The timestamp in this field shows the date/time when the payment dispute was closed, so this field is only returned for payment disputes in the CLOSED state. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also k |
| paymentDisputeSummaries.openDate | string | No | The timestamp in this field shows the date/time when the payment dispute was opened. This field is returned for payment disputes in all states. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenw |
| paymentDisputeSummaries.orderId | string | No | This is the unique identifier of the order involved in the payment dispute. |
| paymentDisputeSummaries.paymentDisputeId | string | No | This is the unique identifier of the payment dispute. This identifier is automatically created by eBay once the payment dispute comes into the eBay system. This identifier is passed in at the end of the getPaymentDispute call URI to retrieve a specific payment dispute. The getPaymentDispute method r |
| paymentDisputeSummaries.paymentDisputeStatus | string | No | The enumeration value in this field gives the current status of the payment dispute. For implementation help, refer to eBay API documentation |
| paymentDisputeSummaries.reason | string | No | The enumeration value in this field gives the reason why the buyer initiated the payment dispute. See DisputeReasonEnum type for a description of the supported reasons that buyers can give for initiating a payment dispute. For implementation help, refer to eBay API documentation |
| paymentDisputeSummaries.respondByDate | string | No | The timestamp in this field shows the date/time when the seller must response to a payment dispute, so this field is only returned for payment disputes in the ACTION_NEEDED state. For payment disputes that require action by the seller, that same seller must call getPaymentDispute to see the next act |
| prev | string | No | The getPaymentDisputeSummaries call URI to use if you wish to view the previous page of the result set. For example, the following URI returns records 1 thru 10 from the collection of payment disputes: path/payment_dispute_summary?limit=10&offset=0 This field is only returned if there is a previous  |
| total | integer | No | This integer value is the total number of payment disputes that matched the input criteria. If the total number of entries exceeds the value that was set for limit in the request payload, you will have to make multiple API calls to see all pages of the results set. This field is returned even if it  |
