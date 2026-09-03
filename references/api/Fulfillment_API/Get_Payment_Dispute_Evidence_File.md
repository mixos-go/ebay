---
title: Get_Payment_Dispute_Evidence_File
category: Fulfillment_API
api_name: Get_Payment_Dispute_Evidence_File
method: GET
path: /payment_dispute/{payment_dispute_id}/fetch_evidence_content
---

**Category:** Fulfillment_API
**API:** Get_Payment_Dispute_Evidence_File

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/fetch_evidence_content

## API Description
Get Payment Dispute Evidence File

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This path parameter is used to specify the unique identifier of the payment dispute associated with the evidence file being retrieved. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |
| evidence_id (query) | string | Yes | This query parameter is used to specify the unique identifier of the evidential file set. The identifier of an evidential file set for a payment dispute is returned under the evidence array in the getPaymentDispute response. |
| file_id (query) | string | Yes | This query parameter is used to specify the unique identifier of an evidential file. This file must belong to the evidential file set identified through the evidence_id query parameter. The identifier of each evidential file is returned under the evidence.files array in the getPaymentDispute respons |

## Response
_No documented response fields._
