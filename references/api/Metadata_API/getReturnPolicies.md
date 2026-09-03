---
title: getReturnPolicies
category: Metadata_API
api_name: getReturnPolicies
method: GET
path: /marketplace/{marketplace_id}/get_return_policies
---

**Category:** Metadata_API
**API:** getReturnPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_return_policies

## API Description
This method returns the eBay policies that define whether or not you must include a return policy for the items you list in the categories of a specific marketplace, plus the guidelines for creating domestic and international return policies in the different eBay categories. By default, this method returns the entire category tree for the specified marketplace. You can limit the size of the result set by using the filter query parameter to specify only the category IDs you want to review. Tip: This method can potentially return a very large response payload. eBay recommends that the response payload be compressed by passing in the Accept-Encoding request header and setting the value to gzip .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | This query parameter limits the response by returning policy information for only the selected sections of the category tree. Supply categoryId values for the sections of the tree you want returned. When you specify a categoryId value, the returned category tree includes the policies for that parent |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information is retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Encoding (header) | string | No | This header indicates the compression-encoding algorithms the client accepts for the response. This value should be set to gzip . For more information, refer to HTTP request headers . |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| returnPolicies | array<ReturnPolicy> | No | A list of elements, where each contains a category ID and a flag that indicates whether or not listings in that category require a return policy. |
| returnPolicies.categoryId | string | No | The category ID to which the return policies apply. |
| returnPolicies.categoryTreeId | string | No | A value that indicates the root node of the category tree used for the response set. Each marketplace is based on a category tree whose root node is indicated by this unique category ID value. All category policy information returned by this call pertains to the categories included below this root n |
| returnPolicies.domestic | ReturnPolicyDetails | No | This complex type defines the category policies related to domestic item returns. |
| returnPolicies.domestic.policyDescriptionEnabled | boolean | No | If set to true , this flag indicates you can supply a detailed return policy description within your return policy (for example, by populating the returnInstructions field in the Account API's createReturnPolicy ). User-supplied return policy details are allowed only in the DE, ES, FR, and IT market |
| returnPolicies.domestic.refundMethods | array<string> | No | A list of refund methods allowed for the associated category. Note: Depending on the API used to setup your return policy, available refund methods are defined differently. Account v1 API When using the createReturnPolicy and updateReturnPolicy methods to create/manage business policies, use the app |
| returnPolicies.domestic.returnMethods | array<string> | No | A list of return methods allowed for the associated category. Note: Depending on the API used to setup your return policy, available return methods are defined differently. Account v1 API When using createReturnPolicy and updateReturnPolicy to create/manage business policies, use returnMethod and in |
| returnPolicies.domestic.returnPeriods | array<TimeDuration> | No | A list of return periods allowed for the associated category. Note: Depending on the API used to setup your return policy, return periods are defined differently. Account v1 API When using createReturnPolicy and updateReturnPolicy to create/manage business policies, use the returnPeriod and internat |
| returnPolicies.domestic.returnPeriods.unit | string | No | A time-measurement unit that specifies a singular period of time. A span of time is defined when you apply the value specified in the value field to the value specified for unit . Time-measurement units can be YEAR, MONTH, DAY, and so on. See TimeDurationUnitEnum for a complete list of possible time |
| returnPolicies.domestic.returnPeriods.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnPolicies.domestic.returnsAcceptanceEnabled | boolean | No | A value of true in this field indicates that return policies are applicable to the corresponding leaf category. Note: Depending on the API used to setup your return policy, whether or not you accept returns is configured as follows: Account v1 API When using createReturnPolicy and updateReturnPolicy |
| returnPolicies.domestic.returnShippingCostPayers | array<string> | No | A list of allowed values for who pays for the return shipping cost. Note that for SNAD returns, the seller is always responsible for the return shipping cost. Note: Depending on the API used to setup your return policy, specifiying that the buyer or seller is responsible for paying for return shippi |
| returnPolicies.international | ReturnPolicyDetails | No | This complex type defines the category policies related to international item returns. |
| returnPolicies.international.policyDescriptionEnabled | boolean | No | If set to true , this flag indicates you can supply a detailed return policy description within your return policy (for example, by populating the returnInstructions field in the Account API's createReturnPolicy ). User-supplied return policy details are allowed only in the DE, ES, FR, and IT market |
| returnPolicies.international.refundMethods | array<string> | No | A list of refund methods allowed for the associated category. Note: Depending on the API used to setup your return policy, available refund methods are defined differently. Account v1 API When using the createReturnPolicy and updateReturnPolicy methods to create/manage business policies, use the app |
| returnPolicies.international.returnMethods | array<string> | No | A list of return methods allowed for the associated category. Note: Depending on the API used to setup your return policy, available return methods are defined differently. Account v1 API When using createReturnPolicy and updateReturnPolicy to create/manage business policies, use returnMethod and in |
| returnPolicies.international.returnPeriods | array<TimeDuration> | No | A list of return periods allowed for the associated category. Note: Depending on the API used to setup your return policy, return periods are defined differently. Account v1 API When using createReturnPolicy and updateReturnPolicy to create/manage business policies, use the returnPeriod and internat |
| returnPolicies.international.returnPeriods.unit | string | No | A time-measurement unit that specifies a singular period of time. A span of time is defined when you apply the value specified in the value field to the value specified for unit . Time-measurement units can be YEAR, MONTH, DAY, and so on. See TimeDurationUnitEnum for a complete list of possible time |
| returnPolicies.international.returnPeriods.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| returnPolicies.international.returnsAcceptanceEnabled | boolean | No | A value of true in this field indicates that return policies are applicable to the corresponding leaf category. Note: Depending on the API used to setup your return policy, whether or not you accept returns is configured as follows: Account v1 API When using createReturnPolicy and updateReturnPolicy |
| returnPolicies.international.returnShippingCostPayers | array<string> | No | A list of allowed values for who pays for the return shipping cost. Note that for SNAD returns, the seller is always responsible for the return shipping cost. Note: Depending on the API used to setup your return policy, specifiying that the buyer or seller is responsible for paying for return shippi |
| returnPolicies.required | boolean | No | If set to true , this flag indicates that you must specify a return policy for items listed in the associated category. Note that not accepting returns (setting returnsAcceptedEnabled to false ) is a valid return policy. |
| warnings | array<Error> | No | A list of the warnings that were generated as a result of the request. This field is not returned if no warnings were generated by the request. |
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
