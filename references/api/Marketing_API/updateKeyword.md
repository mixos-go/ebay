---
title: updateKeyword
category: Marketing_API
api_name: updateKeyword
method: PUT
path: /ad_campaign/{campaign_id}/keyword/{keyword_id}
---

**Category:** Marketing_API
**API:** updateKeyword

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/keyword/{keyword_id}

## API Description
This method updates keywords using a campaign ID and keyword ID for an existing priority strategy campaign. In the request, specify the campaign_id and keyword_id as path parameters. Call the getCampaigns method to retrieve a list of current campaign IDs for a seller and call the getKeywords method to retrieve their keyword IDs.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the keyword being updated. Use the getCampaigns method to retrieve campaign IDs. |
| keyword_id (path) | string | Yes | This path parameter specifies the unique identifier of the keyword being updated. Use the getKeywords method to retrieve keyword IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| bid | Amount | No | This container is used to set or change the bid for the keyword. Each time a listing is retrieved in search results using this keyword and clicked on, the seller will be charged this amount. Each click goes toward the daily budget set up for the CPC campaign. If the bid is not provided, then the def |
| bid.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| bid.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| keywordStatus | string | No | Include this field if you wish to change the status of the keyword. The status value specified here must be different than the keyword's current status. To confirm the current status of a keyword, you can use the getKeyword method. If the status of the ad is currently ACTIVE , you can change status  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| errors | array<Error> | No | This container will be returned if there are one or more issues associated with modifying the corresponding keyword. |
| errors.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| errors.domain | string | No | Name of the domain containing the service or application. |
| errors.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| errors.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| errors.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| errors.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| errors.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| errors.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| errors.parameters.name | string | No | Name of the entity that threw the error. |
| errors.parameters.value | string | No | A description of the error. |
| errors.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
| keywordId | string | No | This field identifies the keyword that the seller updated, or attempted to update. |
| statusCode | integer | No | An HTTP status code is returned for each keyword to indicate the success or failure of updating that keyword. |
| warnings | array<Error> | No | List of warnings associated with this operation |
| warnings.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| warnings.domain | string | No | Name of the domain containing the service or application. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| warnings.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the entity that threw the error. |
| warnings.parameters.value | string | No | A description of the error. |
| warnings.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
