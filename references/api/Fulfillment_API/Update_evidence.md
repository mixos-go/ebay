---
title: Update_evidence
category: Fulfillment_API
api_name: Update_evidence
method: POST
path: /payment_dispute/{payment_dispute_id}/update_evidence
---

**Category:** Fulfillment_API
**API:** Update_evidence

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/update_evidence

## API Description
Update evidence

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the contested payment dispute for which the user plans to update the evidence set. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| evidenceId | string | No | The unique identifier of the evidence set that is being updated with new evidence files. This ID is returned under the evidence array in the getPaymentDispute response. |
| evidenceType | string | No | This field is used to indicate the type of evidence being provided through one or more evidence files. All evidence files (if more than one) should be associated with the evidence type passed in this field. See the EvidenceTypeEnum type for the supported evidence types. For implementation help, refe |
| files | array<FileEvidence> | No | This array is used to specify one or more evidence files that will be added to the evidence set associated with a payment dispute. At least one evidence file must be specified in the files array. The unique identifier of an evidence file is returned in the response payload of the uploadEvidence meth |
| files.fileId | string | No | This field is used to identify the evidence file to be uploaded to the evidence set. This file is created with the uploadEvidenceFile method and can be retrieved using the getPaymentDisputes method. |
| lineItems | array<OrderLineItems> | No | This required array identifies the order line item(s) for which the evidence file(s) will be applicable. These values are returned under the evidenceRequests.lineItems array in the getPaymentDispute response. Note: Both the itemId and lineItemID fields are needed to identify each order line item. |
| lineItems.itemId | string | No | The unique identifier of the eBay listing associated with the order. |
| lineItems.lineItemId | string | No | The unique identifier of the line item within the order. |

## Response
_No documented response fields._
