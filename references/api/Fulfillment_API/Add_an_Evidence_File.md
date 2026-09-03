---
title: Add_an_Evidence_File
category: Fulfillment_API
api_name: Add_an_Evidence_File
method: POST
path: /payment_dispute/{payment_dispute_id}/add_evidence
---

**Category:** Fulfillment_API
**API:** Add_an_Evidence_File

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/add_evidence

## API Description
Add an Evidence File

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the contested payment dispute for which the seller wishes to add evidence files. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| evidenceType | string | No | This field is used to indicate the type of evidence being provided through one or more evidence files. All evidence files (if more than one) should be associated with the evidence type passed in this field. See the EvidenceTypeEnum type for the supported evidence types. For implementation help, refe |
| files | array<FileEvidence> | No | This array is used to specify one or more evidence files that will become part of a new evidence set associated with a payment dispute. At least one evidence file must be specified in the files array. |
| files.fileId | string | No | This field is used to identify the evidence file to be uploaded to the evidence set. This file is created with the uploadEvidenceFile method and can be retrieved using the getPaymentDisputes method. |
| lineItems | array<OrderLineItems> | No | This array identifies the order line item(s) for which the evidence file(s) will be applicable. These values are returned under the evidenceRequests.lineItems array in the getPaymentDispute response. |
| lineItems.itemId | string | No | The unique identifier of the eBay listing associated with the order. |
| lineItems.lineItemId | string | No | The unique identifier of the line item within the order. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| evidenceId | string | No | The value returned in this field is the unique identifier of the newly-created evidence set. Upon a successful call, this value is automatically genererated. This new evidence set for the payment dispute includes the evidence file(s) that were passed in to the fileId array in the request payload. Th |
