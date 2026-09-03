---
title: removePostOrderDocument
category: Media_API
api_name: removePostOrderDocument
method: DELETE
path: /post_order/document/{document_id}
---

**Category:** Media_API
**API:** removePostOrderDocument

**Method:** DELETE
**HTTP Path:** https://apim.ebay.com{basePath}/post_order/document/{document_id}

## API Description
This method deletes a previously uploaded document by its document ID. Only documents in SUBMITTED state can be removed; documents in the PUBLISHED state cannot be deleted. Note: After a document is uploaded (but not yet published), its status is SUBMITTED . When its identifier is associated with a post‑order entity through an eBay GraphQL mutation, the status changes to PUBLISHED . A post-order entity is part of eBay's order management for activities after purchase (such as returns). Important! All documents, whether submitted or published, expire and become inaccessible after their expiration date.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| document_id (path) | string | Yes | This path parameter is the unique identifier of the document associated with the file to be deleted. This ID was returned in the Location response header when calling the uploadPostOrderDocument method to upload the document. |

## Response
_No documented response fields._
