---
title: getCategoryPolicies
category: Metadata_API
api_name: getCategoryPolicies
method: GET
path: /marketplace/{marketplace_id}/get_category_policies
---

**Category:** Metadata_API
**API:** getCategoryPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_category_policies

## API Description
This method returns eBay category policy metadata for all leaf categories on the specified marketplace. By default, this method returns metadata on all leaf categories. You can limit the size of the result set by using the filter query parameter to specify only the leaf category IDs you want to review. If you specify a valid marketplace ID but that marketplace does not contain policy information, or if you filter out all results, a successful call returns a 204 No content status code with an empty response body.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | This query parameter limits the response by only returning metadata for the specified leaf categories. Supply the categoryId for one or more leaf categories. You can verify if a category is a leaf category by using the Taxonomy API and looking for a "leafCategory": true tag. The parameter takes a li |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information is retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryPolicies | array<CategoryPolicy> | No | This array contains applicable policy metadata for the leaf categories returned for the marketplace specified in the path parameter marketplace_id and optionally limited by only those leaf category IDs specified in the query parameter filter . |
| categoryPolicies.autoPayEnabled | boolean | No | If this field is returned as true , the corresponding category supports immediate payment for listings. The immediate payment feature is applicable to fixed-price listings, to auction listings with the 'Buy It Now' option enabled, and for a motor vehicle listing that requires an initial deposit. If  |
| categoryPolicies.b2bVatEnabled | boolean | No | If this field is returned as true , the corresponding category supports business-to-business (B2B) VAT listings. If this field is not present, the category does not have B2B VAT listings. This feature is applicable to the eBay Germany (DE), Austria (AT), and Switzerland (CH) sites only. This field i |
| categoryPolicies.categoryId | string | No | The unique identifier of the eBay leaf category for which metadata is being returned. |
| categoryPolicies.categoryTreeId | string | No | The unique identifier of the category tree. |
| categoryPolicies.eanSupport | string | No | This enumerated value indicates whether or not European Article Numbers (EANs) are supported/required when listing products in the category. For implementation help, refer to eBay API documentation |
| categoryPolicies.expired | boolean | No | If this field is returned as true , the corresponding category is no longer a valid eBay category on the site, and items may not be listed in this category. You can use the getExpiredCategories method (of the Taxonomy API ) to find the leaf category that replaced the expired category. This field is  |
| categoryPolicies.intangibleEnabled | boolean | No | If this field is returned as true , the category supports the listing of intangible goods or services. |
| categoryPolicies.isbnSupport | string | No | This enumerated value indicates whether or not International Standard Book Numbers (ISBNs) are supported/required when listing products in the specified category. For implementation help, refer to eBay API documentation |
| categoryPolicies.lsd | boolean | No | If this field (Lot Size Disabled) is returned as true , the corresponding category does not support lot listings. A lot listing is a listing that features multiple related items that must be purchased by one buyer in one transaction. This field is only returned when true (not returned when false). |
| categoryPolicies.minimumReservePrice | number | No | Indicates the Minimum Reserve Price for an auction listing in this category. If there is no Minimum Reserve Price, a value of 0.0 is returned in this field. |
| categoryPolicies.orpa | boolean | No | This field (Override Reserve Price Allowed) is returned as true if the eBay marketplace's default policy is to allow reserve prices for auction listings, but the corresponding category does not allow a reserve price. Note: This field is not returned if the marketplace does not permit reserve prices. |
| categoryPolicies.orra | boolean | No | If this field (Override Reduce Reserve Allowed) is returned as true , the seller can reduce or remove a reserve price that had already been reduced for an active auction listing. |
| categoryPolicies.paymentMethods | array<string> | No | An array that indicates the acceptable offline payment methods that can be used when listing an item for sale in the corresponding category. |
| categoryPolicies.reduceReserveAllowed | boolean | No | If this field (Reduce Reserve Allowed) is true , the corresponding leaf category allows the seller to reduce an item's reserve price. If false, this field is not returned in the response and the corresponding leaf category on the site do not normally allow sellers to reduce an item's reserve price.  |
| categoryPolicies.reservePriceAllowed | boolean | No | This field indicates whether reserve prices are allowed for auction listings in this category. This field returns as true when the category supports reserve prices, or false if the eBay marketplace does not permit reserve prices or the category override blocks reserve prices ( orpa is true ). |
| categoryPolicies.upcSupport | string | No | This enumerated value indicates whether or not the category on the specified eBay site supports the use of Universal Product Codes (UPCs) to help create a listing. For implementation help, refer to eBay API documentation |
| categoryPolicies.valueCategory | boolean | No | When returned as true , this boolean indicates that the leaf category for the specified site is designated by eBay as a value category. Value categories can be used as a secondary category for a listing at no extra charge. |
| categoryPolicies.virtual | boolean | No | If this field is returned as true , the corresponding category is an eBay virtual category, a category in which items may not be listed. This field is only returned when true (not returned when false). |
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
