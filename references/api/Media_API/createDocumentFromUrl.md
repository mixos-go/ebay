---
title: createDocumentFromUrl
category: Media_API
api_name: createDocumentFromUrl
method: POST
path: /document/create_document_from_url
---

**Category:** Media_API
**API:** createDocumentFromUrl

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/document/create_document_from_url

## API Description
This method downloads a document from the provided URL and adds that document to the user's account. This method requires the URL of the document, the type of document to be uploaded, and the language(s) that the document contains. When a document is successfully created, the method returns the HTTP Status Code 201 Created. The method returns documentId in the response payload, which you can use to retrieve the document resource. This ID is also returned in the location header, for convenience. Important! Make sure to capture the document ID value returned in the response payload. This value is required to use the other methods in the document resource, and also needed to associate a document to a listing using the Trading and Inventory APIs. After creating a document using this method, a getDocument call should be made to check for a documentStatus of ACCEPTED . Only documents with this status can be added to a listing. See Managing documents for more information on creating, uploading, and adding documents to listings. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| documentType | string | No | The type of the document being created. For example, a USER_GUIDE_OR_MANUAL or a SAFETY_DATA_SHEET . For implementation help, refer to eBay API documentation |
| documentUrl | string | No | The URL of the document being created. The document referenced by the URL must be a .pdf, .png, .jpg, or .jpeg file, and must be no larger than 10 MB. |
| languages | array<string> | No | This array shows the language(s) used in the document. |

## Response
_No documented response fields._
