---
title: Upload_an_Evidence_File
category: Fulfillment_API
api_name: Upload_an_Evidence_File
method: POST
path: /payment_dispute/{payment_dispute_id}/upload_evidence_file
---

**Category:** Fulfillment_API
**API:** Upload_an_Evidence_File

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/upload_evidence_file

## API Description
Upload an Evidence File

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the contested payment dispute for which the user intends to upload an evidence file. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to multipart/form-data . For more information, refer to HTTP request headers . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| fileId | string | No | This field is used to identify the evidence file to be uploaded to the evidence set. This file is created with the uploadEvidenceFile method and can be retrieved using the getPaymentDisputes method. |
