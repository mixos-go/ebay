---
title: bulkUpdateNegativeKeyword
category: Marketing_API
api_name: bulkUpdateNegativeKeyword
method: POST
path: /bulk_update_negative_keyword
---

**Category:** Marketing_API
**API:** bulkUpdateNegativeKeyword

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_update_negative_keyword

## API Description
This method updates the statuses of existing negative keywords, in bulk. Specify the negativeKeywordId and negativeKeywordStatus in the request body.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<UpdateNegativeKeywordIdRequest> | No | An array to update the statuses of one or more existing negative keywords. |
| requests.negativeKeywordId | string | No | A unique eBay-assigned ID for a negative keyword. This keyword ID will be generated for each successfully created negative keyword. Use the getNegativeKeywords method to retrieve negative keyword IDs. |
| requests.negativeKeywordStatus | string | No | A field that defines the status of the negative keyword. See NegativeKeywordStatusEnum for supported values. For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<UpdateNegativeKeywordResponse> | No | A list of negative keywords that have been processed from the bulk request. |
| responses.errors | array<Error> | No | A container that will be returned if there are one or more issues associated with modifying the corresponding negative keyword. |
| responses.errors.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| responses.errors.domain | string | No | Name of the domain containing the service or application. |
| responses.errors.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| responses.errors.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| responses.errors.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| responses.errors.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| responses.errors.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| responses.errors.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| responses.errors.parameters.name | string | No | Name of the entity that threw the error. |
| responses.errors.parameters.value | string | No | A description of the error. |
| responses.errors.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
| responses.negativeKeywordId | string | No | A unique eBay-assigned ID for a negative keyword. This keyword ID will be generated for each successfully created negative keyword. |
| responses.statusCode | integer | No | An HTTP status code that indicates the success or failure of updating that negative keyword. |
