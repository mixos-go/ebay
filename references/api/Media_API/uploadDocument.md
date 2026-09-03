---
title: uploadDocument
category: Media_API
api_name: uploadDocument
method: POST
path: /document/{document_id}/upload
---

**Category:** Media_API
**API:** uploadDocument

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/document/{document_id}/upload

## API Description
This method associates the specified file with the specified document ID and uploads the input file. After the file has been uploaded, the processing of the file begins. Supported file types include .PDF, .JPEG/.JPG, and .PNG, with a maximum file size of 10 MB (10485760 bytes). Note: Animated and multi-page PNG files are not currently supported. Note: The document ID value returned in the response of the createDocument method is a required input path parameter for this method. This value is also returned in the location header of the createDocument response payload. A successful upload returns the HTTP Status Code 200 OK . See Managing documents for additional information. Note: You must use a Content-Type header with its value set to multipart/form-data . This call does not have a JSON Request payload but uploads the file as form-data. For example: file: @&quot;/C:/Users/.../drone_user_warranty.pdf&quot; See Samples for information. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| document_id (path) | string | Yes | The unique identifier of the document to be uploaded. This value is returned in the response of the createDocument method. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to multipart/form-data . For more information, refer to HTTP request headers . |

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
