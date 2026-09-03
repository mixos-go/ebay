---
title: bulkCreateNegativeKeyword
category: Marketing_API
api_name: bulkCreateNegativeKeyword
method: POST
path: /bulk_create_negative_keyword
---

**Category:** Marketing_API
**API:** bulkCreateNegativeKeyword

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_create_negative_keyword

## API Description
This method adds negative keywords, in bulk, to an existing ad group in a priority strategy campaign that uses manual targeting. Specify the campaignId and adGroupId in the request body, along with the negativeKeywordText and negativeKeywordMatchType . Call the getCampaigns method to retrieve a list of current campaign IDs for a specified seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<CreateNegativeKeywordRequest> | No | This array is used to pass in multiple negative keywords for one or more ad groups that belong to a campaign that uses the Cost Per Click (CPC) funding model. |
| requests.adGroupId | string | No | This adGroupId is created when an ad group is first created and associated with a campaign. This is the ad group to which the corresponding negative keyword will be added. Use the getAdGroups method to retrieve the ad group IDs for a seller. Required if the negative keyword is being created at the a |
| requests.campaignId | string | No | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the set of negative keywords being created. Use the getCampaigns method to retrieve campaign IDs. Required if the negative keyword is being created at the ad group level. |
| requests.negativeKeywordMatchType | string | No | A field that defines the match type for the negative keyword. Note: Broad matching of negative keywords is not currently supported. Valid Values: EXACT PHRASE For implementation help, refer to eBay API documentation |
| requests.negativeKeywordText | string | No | The negative keyword text. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<NegativeKeywordResponse> | No | A list of negative keywords that have been processed by the request. |
| responses.adGroupId | string | No | A unique identifier for an ad group that is generated when an ad group is first created and associated with a campaign. |
| responses.campaignId | string | No | A unique eBay-assigned ID for a campaign. This ID is generated when a campaign is created. |
| responses.errors | array<Error> | No | This container will be returned if there is an issue creating the corresponding negative keyword. |
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
| responses.href | string | No | The URI for the negative keyword, which is used to retrieve the negative keyword. This URI will be returned for each successfully created negative keyword. |
| responses.negativeKeywordId | string | No | A unique eBay-assigned ID for a negative keyword. This negative keyword ID will be generated for each successfully created negative keyword. |
| responses.negativeKeywordMatchType | string | No | The match type for the negative keyword. Note: Broad matching of negative keywords is not currently supported. Valid Values: EXACT PHRASE For implementation help, refer to eBay API documentation |
| responses.negativeKeywordText | string | No | The text for the negative keyword. |
| responses.statusCode | integer | No | The status of the request to create a negative keyword. This field indicates whether the process was successful or not. |
