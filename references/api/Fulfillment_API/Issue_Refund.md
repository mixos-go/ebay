---
title: Issue_Refund
category: Fulfillment_API
api_name: Issue_Refund
method: POST
path: /order/{order_id}/issue_refund
---

**Category:** Fulfillment_API
**API:** Issue_Refund

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/order/{order_id}/issue_refund

## API Description
Issue Refund

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| order_id (path) | string | Yes | This path parameter is used to specify the unique identifier of the order associated with a refund. Use the getOrders method to retrieve order IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| reasonForRefund | string | No | The enumeration value passed into this field indicates the reason for the refund. One of the defined enumeration values in the ReasonForRefundEnum type must be used. This field is required, and it is highly recommended that sellers use the correct refund reason, especially in the case of a buyer-req |
| comment | string | No | This free-text field allows the seller to clarify why the refund is being issued to the buyer. Max Length : 100 |
| refundItems | array<RefundItem> | No | The refundItems array is only required if the seller is issuing a refund for one or more individual order line items in a multiple line item order. Otherwise, the seller just uses the orderLevelRefundAmount container to specify the amount of the refund for the entire order. |
| refundItems.refundAmount | SimpleAmount | No | This container is used to specify the amount of the refund for the corresponding order line item. If a seller wants to issue a refund for an entire order, the seller would use the orderLevelRefundAmount container instead. |
| refundItems.refundAmount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| refundItems.refundAmount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |
| refundItems.lineItemId | string | No | The unique identifier of an order line item. This identifier is created once a buyer purchases a 'Buy It Now' item or if an auction listing ends with a winning bidder. Either this field or the legacyReference container is needed to identify an individual order line item that will receive a refund. T |
| refundItems.legacyReference | LegacyReference | No | This container is needed if the seller is issuing a refund for an individual order line item, and wishes to use an item ID/transaction ID pair to identify the order line item. Either this container or the lineItemId field is needed to identify an individual order line item that will receive a refund |
| refundItems.legacyReference.legacyItemId | string | No | The unique identifier of a listing. This value can be found in the Transaction container in the response of the getOrder call of the Trading API . Note: Both legacyItemId and legacyTransactionId are needed to identify an order line item. |
| refundItems.legacyReference.legacyTransactionId | string | No | The unique identifier of a sale/transaction in legacy/Trading API format. A 'transaction ID' is created once a buyer purchases a 'Buy It Now' item or if an auction listing ends with a winning bidder. This value can be found in the Transaction container in the response of the getOrder call of the Tra |
| orderLevelRefundAmount | SimpleAmount | No | This container is used to specify the amount of the refund for the entire order. If a seller wants to issue a refund for an individual line item within a multiple line item order, the seller would use the refundItems array instead. |
| orderLevelRefundAmount.currency | string | No | A three-letter ISO 4217 code (such as USD for US site) that indicates the currency of the amount in the value field. Both the value and currency fields are always returned with the amount container. For implementation help, refer to eBay API documentation |
| orderLevelRefundAmount.value | string | No | The monetary amount of the payment dispute. Both the value and currency fields are always returned with the amount container. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| refundId | string | No | The unique identifier of the order refund. This value is returned unless the refund operation fails ( refundStatus value shows FAILED ). This identifier can be used to track the status of the refund through a getOrder or getOrders call. For order-level refunds, check the paymentSummary.refunds.refun |
| refundStatus | string | No | The value returned in this field indicates the success or failure of the refund operation. A successful issueRefund operation should result in a value of PENDING . A failed issueRefund operation should result in a value of FAILED , and an HTTP status code and/or and API error code may also get retur |
