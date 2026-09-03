---
title: bulkUpdateAdsStatus
category: Marketing_API
api_name: bulkUpdateAdsStatus
method: POST
path: /ad_campaign/{campaign_id}/bulk_update_ads_status
---

**Category:** Marketing_API
**API:** bulkUpdateAdsStatus

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_campaign/{campaign_id}/bulk_update_ads_status

## API Description
Note: This method is only available for select partners who have been approved for the priority strategy program. For information about how to request access to this program, refer to Priority Strategy Access Requests in the Promoted Listings Playbook. To determine if a seller qualifies for priority strategy, use the getAdvertisingEligibility method in Account API. This method works with listings created with either the Trading API or the Inventory API . This method updates the status of ads in bulk. Specify the campaign_id you want to update as a URI parameter, and configure the adGroupStatus in the request payload.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| campaign_id (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the ad campaign associated with the ad statuses being updated. Use the getCampaigns method to retrieve campaign IDs. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| requests | array<UpdateAdStatusRequest> | No | An array of listing IDs and bid percentages. |
| requests.adId | string | No | A unique eBay-assigned identifier for an ad that belongs to the specified campaign. Use the getAds method to retrieve ad IDs. |
| requests.adStatus | string | No | An enumeration value representing the status you wish to update the specified ad to. Valid Values: ACTIVE PAUSED ARCHIVED For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responses | array<AdUpdateStatusResponse> | No | An array of processed ad listings in bulk. |
| responses.adId | string | No | A unique eBay-assigned ID that is generated when the ad is created. |
| responses.errors | array<Error> | No | A list of errors associated with the specified listing ID. |
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
| responses.href | string | No | The URI for the ad, which can be used to retrieve the ad. |
| responses.statusCode | integer | No | An HTTP status code that indicates the response-status of the request. |
