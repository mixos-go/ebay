---
title: bulkCreateKeyword
category: Marketing_API
api_name: bulkCreateKeyword
method: POST
path: /ad_campaign/{campaign_id}/bulk_create_keyword
---

**Category:** Marketing_API
**API:** bulkCreateKeyword

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/bulk_create_keyword

## API Description
This method adds keywords, in bulk, to an existing priority strategy ad group in a campaign that uses manual targeting. This method also sets the CPC rate for each keyword, depending on the selected bidding strategy, as follows: FIXED : If the seller provides a keyword bid, that bid value will be used. If no bid is provided, the adgroup's default bid value will be used. DYNAMIC : The eBay suggested bid will be used. If the seller passes in a value, a warning will be returned. In the request, supply the campaign_id as a path parameter. Call the getCampaigns method to retrieve a list of current campaign IDs for a specified seller.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign for which a set of keywords is being created. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<CreateKeywordRequest> | No | This array is used to pass in multiple keywords for one or more ad groups that belong to a campaign that uses the Cost Per Click (CPC) funding model. Up to {max value} keywords can be created with one call. |
| requests.adGroupId | string | No | This adGroupId is created when an ad group is first created and associated with a campaign. This is the ad group that the corresponding keyword will be added to. This ad group must be a part of the campaign that is specified in the call URI. Use the getAdGroups method to retrieve the ad group IDs fo |
| requests.bid | Amount | No | This container is used to set the maximum bid for the keyword. Each time a listing is retrieved in search results using this keyword and clicked on, the seller will be charged, at most, this amount. Each click goes toward the daily budget set up for the CPC campaign. If the bid is not provided, then |
| requests.bid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| requests.bid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| requests.keywordText | string | No | The text of the keyword. Keywords are not case sensitive and compound words can be used without additional encoding (for example, tennis ball). Maximum number of characters: 100 Maximum number of words: 10 |
| requests.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<KeywordResponse> | No | A list of keywords that have been processed by the request. |
| responses.adGroupId | string | No | The identifier of the ad group that the keyword was added to. |
| responses.errors | array<Error> | No | This container will be returned if there is an issue creating the corresponding keyword and/or adding that keyword to the corresponding ad group. |
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
| responses.href | string | No | The getKeyword URI for the keyword, which is used to retrieve the keyword. This URI will be returned for each successfully created keyword. |
| responses.keywordId | string | No | A unique eBay-assigned ID for a keyword that is generated for an ad group. This keyword ID will be generated for each successfully created keyword. |
| responses.keywordText | string | No | The text of the keyword. |
| responses.matchType | string | No | A field that defines the match type for the keyword. Valid Values: BROAD EXACT PHRASE For implementation help, refer to eBay API documentation |
| responses.statusCode | integer | No | An HTTP status code is returned for each keyword to indicate the success or failure of adding that keyword to the ad group. |
| responses.warnings | array<Error> | No | List of warnings associated with this operation |
| responses.warnings.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| responses.warnings.domain | string | No | Name of the domain containing the service or application. |
| responses.warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| responses.warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| responses.warnings.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| responses.warnings.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| responses.warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| responses.warnings.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| responses.warnings.parameters.name | string | No | Name of the entity that threw the error. |
| responses.warnings.parameters.value | string | No | A description of the error. |
| responses.warnings.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
