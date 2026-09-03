---
title: getExtendedProducerResponsibilityPolicies
category: Metadata_API
api_name: getExtendedProducerResponsibilityPolicies
method: GET
path: /marketplace/{marketplace_id}/get_extended_producer_responsibility_policies
---

**Category:** Metadata_API
**API:** getExtendedProducerResponsibilityPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_extended_producer_responsibility_policies

## API Description
This method returns the Extended Producer Responsibility policies for one, multiple, or all eBay categories in an eBay marketplace. The identifier of the eBay marketplace is passed in as a path parameter, and unless one or more eBay category IDs are passed in through the filter query parameter, this method will return metadata on every applicable category for the specified marketplace. Note: Currently, the Extended Producer Responsibility policies are only applicable to a limited number of categories. Note: Extended Producer Responsibility IDs are no longer set at the listing level so category-level metadata is no longer returned. Instead, sellers will provide/manage these IDs at the account level by going to Account Settings . Tip: This method can potentially return a very large response payload. eBay recommends that the response payload be compressed by passing in the Accept-Encoding request header and setting the value to gzip .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | A query parameter that can be used to limit the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree that should be returned. When a categoryId value is specified, the returned category tree includes the p |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information shall be retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Encoding (header) | string | No | This header indicates the compression-encoding algorithms the client accepts for the response. This value should be set to gzip . For more information, refer to HTTP request headers . |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| extendedProducerResponsibilities | array<ExtendedProducerResponsibilityPolicy> | No | An array of response fields detailing the Extended Producer Responsibility policies supported for the specified marketplace. |
| extendedProducerResponsibilities.categoryId | string | No | The unique identifier for the category under which the policy applies. |
| extendedProducerResponsibilities.categoryTreeId | string | No | The unique identifier for the category tree under which the policy applies. |
| extendedProducerResponsibilities.supportedAttributes | array<ExtendedProducerResponsibility> | No | The details regarding the attributes included in the policy, such as their usage guidelines and whether they can be specified at the listing variation level. |
| extendedProducerResponsibilities.supportedAttributes.enabledForVariations | boolean | No | An indication of whether the attribute can be enabled for listing variations. If the value is true , the attribute may be specified at the variation level. |
| extendedProducerResponsibilities.supportedAttributes.name | string | No | The name of the attribute included in the policy. For implementation help, refer to eBay API documentation |
| extendedProducerResponsibilities.supportedAttributes.usage | string | No | The usage guidelines for the attribute, in the specified marketplace. For implementation help, refer to eBay API documentation |
| warnings | array<Error> | No | A collection of warnings generated for the request. |
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
