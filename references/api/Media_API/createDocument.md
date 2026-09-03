---
title: createDocument
category: Media_API
api_name: createDocument
method: POST
path: /document
---

**Category:** Media_API
**API:** createDocument

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/document

## API Description
This method stages a document to be uploaded, and requires the type of document to be uploaded, and the language(s) that the document contains. A successful call returns a documentId value that is then used as a path parameter in an uploadDocument call. When a document is successfully created, the method returns the HTTP Status Code 201 Created. The method returns documentId in the response payload, which you can use to retrieve the document resource. This ID is also returned in the location header, for convenience. Important! Make sure to capture the document ID value returned in the response payload. This value is required to use the other methods in the document resource, and also needed to associate a document to a listing using the Trading and Inventory APIs. To upload a created document, use the document ID returned from this method's response with the uploadDocument method. See Managing documents for information on creating, uploading, and adding documents to listings. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| documentType | string | No | The type of the document being uploaded. For example, a USER_GUIDE_OR_MANUAL or a SAFETY_DATA_SHEET . For implementation help, refer to eBay API documentation |
| languages | array<string> | No | This array shows the language(s) used in the document. |

## Response
_No documented response fields._
