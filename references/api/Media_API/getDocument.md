---
title: getDocument
category: Media_API
api_name: getDocument
method: GET
path: /document/{document_id}
---

**Category:** Media_API
**API:** getDocument

**Method:** GET
**HTTP Path:** https://apim.ebay.com{basePath}/document/{document_id}

## API Description
This method retrieves the current status and metadata of the specified document. Important! The document ID value returned in the response payload of the createDocument method is a required input path parameter for this method. See Managing documents for additional information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| document_id (path) | string | Yes | The unique identifier of the document for which status and metadata is being retrieved. This value is returned in the response of the createDocument method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| documentId | string | No | The unique ID of the document. |
| documentMetadata | DocumentMetadata | No | This container provides the name, size, and type of the specified file. |
| documentMetadata.fileName | string | No | The name of the file including its extension (for example, drone_user_warranty.pdf ). |
| documentMetadata.fileSize | string | No | The size, in bytes, of the document content. |
| documentMetadata.fileType | string | No | The type of the file uploaded. Supported file types include the following: pdf , jpeg , jpg , and png . |
| documentStatus | string | No | The status of the document resource. Once a document has been uploaded using the uploadDocument method, the documentStatus will be SUBMITTED . The document will then either be accepted or rejected. Only documents with the status of ACCEPTED are available to be added to a listing. For implementation  |
| documentType | string | No | The type of the document uploaded. For example, USER_GUIDE_OR_MANUAL . For implementation help, refer to eBay API documentation |
| languages | array<string> | No | This array shows the language(s) used in the document. |
