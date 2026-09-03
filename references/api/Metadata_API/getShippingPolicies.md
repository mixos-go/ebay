---
title: getShippingPolicies
category: Metadata_API
api_name: getShippingPolicies
method: GET
path: /marketplace/{marketplace_id}/get_shipping_policies
---

**Category:** Metadata_API
**API:** getShippingPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_shipping_policies

## API Description
This method returns eBay shipping policy metadata for all leaf categories on the specified marketplace. By default, this method returns metadata on all leaf categories. You can limit the size of the result set by using the filter query parameter to specify only the leaf category IDs you want to review. If you specify a valid marketplace ID but that marketplace does not contain policy information, or if you filter out all results, a successful call returns a 204 No content status code with an empty response body.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | This query parameter limits the response by only returning metadata for the specified leaf categories. Supply the categoryId for one or more leaf categories. You can verify if a category is a leaf category by using the Taxonomy API and looking for a "leafCategory": true tag. The parameter takes a li |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information is retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shippingPolicies | array<ShippingPolicy> | No | This array contains applicable policy metadata for the leaf categories returned for the marketplace specified in the path parameter marketplace_id and optionally limited by only those leaf category IDs specified in the query parameter filter . |
| shippingPolicies.categoryId | string | No | The unique identifier of the eBay leaf category for which metadata is being returned. |
| shippingPolicies.categoryTreeId | string | No | The unique identifier of the category tree. |
| shippingPolicies.globalShippingEnabled | boolean | No | Indicates if the Global Shipping Program (GSP) is supported for the category. Note: GSP is only supported by the eBay UK marketplace ( EBAY_GB ). |
| shippingPolicies.group1MaxFlatShippingCost | Amount | No | Returns the applicable max cap per shipping cost for shipping service group1. |
| shippingPolicies.group1MaxFlatShippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| shippingPolicies.group1MaxFlatShippingCost.value | string | No | The monetary amount, in the currency specified by the currency field. |
| shippingPolicies.group2MaxFlatShippingCost | Amount | No | Returns the applicable max cap per shipping cost for shipping service group2. |
| shippingPolicies.group2MaxFlatShippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| shippingPolicies.group2MaxFlatShippingCost.value | string | No | The monetary amount, in the currency specified by the currency field. |
| shippingPolicies.group3MaxFlatShippingCost | Amount | No | Returns the applicable max cap per shipping cost for shipping service group3. |
| shippingPolicies.group3MaxFlatShippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| shippingPolicies.group3MaxFlatShippingCost.value | string | No | The monetary amount, in the currency specified by the currency field. |
| shippingPolicies.handlingTimeEnabled | boolean | No | Indicates if a seller's stated handling time is enabled for a category. A handling time is generally needed for items that are shipped to the buyer, but not necessarily applicable to freight shipping or local pickup. |
| shippingPolicies.maxFlatShippingCost | Amount | No | The maximum cost the seller can charge for the first domestic flat-rate shipping service. Mutually exclusive with the GroupNMaxFlatShippingCost elements. |
| shippingPolicies.maxFlatShippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| shippingPolicies.maxFlatShippingCost.value | string | No | The monetary amount, in the currency specified by the currency field. |
| shippingPolicies.shippingTermsRequired | boolean | No | Indicates whether the category requires sellers to specify shipping details at listing time. |
| warnings | array<Error> | No | An array of the warnings that were generated as a result of the request. This field is not returned if no warnings were generated by the request. |
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
