---
title: downloadPostOrderDocument
category: Media_API
api_name: downloadPostOrderDocument
method: GET
path: /post_order/document/{document_id}
---

**Category:** Media_API
**API:** downloadPostOrderDocument

**Method:** GET
**HTTP Path:** https://apim.ebay.com{basePath}/post_order/document/{document_id}

## API Description
This method downloads the file associated with the specified document ID. Access depends on the document’s state: SUBMITTED: Only the document owner can download it PUBLISHED: The document is no longer restricted to the owner and can be downloaded by authorized parties involved in the specific post‑order flow based on the documentUsageType Note: After a document is uploaded (but not yet published), its status is SUBMITTED . Once its identifier is linked to a post‑order entity through an eBay GraphQL mutation, the status changes to PUBLISHED . A post-order entity is part of eBay's order management for activities after purchase (such as returns). Important! The document must be in the SUBMITTED or PUBLISHED state to be downloadable. All documents (published or submitted) expire and become inaccessible after their expiration date.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| document_id (path) | string | Yes | This path parameter is the unique identifier of the document associated with the file to be downloaded. This ID was returned in the Location response header when calling the uploadPostOrderDocument method to upload the document. |

## Response
_No documented response fields._
