---
title: uploadPostOrderDocument
category: Media_API
api_name: uploadPostOrderDocument
method: POST
path: /post_order/document
---

**Category:** Media_API
**API:** uploadPostOrderDocument

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/post_order/document

## API Description
This method uploads a document for post‑order processes (for example, a seller providing a return shipping label). Supported file types include .PDF, .JPEG/.JPG, .BMP, .GIF and .PNG, with a maximum file size of 5&nbsp;MB&nbsp;(5,242,880&nbsp;bytes). Note: Animated and multi-page PNG files are not currently supported. For multi-page content, use PDF. The maximum number of pages allowed varies by the documentUsageType . Send a multipart/form‑data request with: file : the document file ( key: file ) documentUsageType : for example, RETURN_SHIPPING_LABEL entityType : for example, RETURNS entityId : the unique identifier for the post-order entity A successful call returns the HTTP Status Code 201 Created with the document ID in the Location header (no response body is returned). The document’s initial state is SUBMITTED . When its identifier is associated with a post-order entity through an eBay GraphQL mutation, the state changes to PUBLISHED . Note: A post-order entity is part of eBay's order management for activities after purchase (such as returns). Important! Capture and retain the documentId in the response’s Location header . It is required to use the other post_order methods and to associate the document with a post-order entity. All documents (published or submitted) expire and become inaccessible after their expiration date. All POST methods in the Media API , including this method, are subject to short-duration, user-level rate limits: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to multipart/form-data . For more information, refer to HTTP request headers . |

## Response
_No documented response fields._
