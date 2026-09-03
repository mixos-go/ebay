---
title: getAdvertisingEligibility
category: Account_v1_API
api_name: getAdvertisingEligibility
method: GET
path: /advertising_eligibility
---

**Category:** Account_v1_API
**API:** getAdvertisingEligibility

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/advertising_eligibility

## API Description
This method allows developers to check the seller eligibility status for eBay advertising programs.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| program_types (query) | string | No | A comma-separated list of eBay advertising programs for which eligibility status will be returned. See the AdvertisingProgramEnum type for a list of supported values. If no programs are specified, the results will be returned for all programs. |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The unique identifier of the eBay marketplace for which the seller eligibility status shall be checked. This header is required or the call will fail. See the MarketplaceIdEnum type for the supported marketplace ID values. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| advertisingEligibility | array<SellerEligibilityResponse> | No | An array of response fields that define the seller eligibility for eBay advertising programs. |
| advertisingEligibility.programType | string | No | The eBay advertising program for which a seller may be eligible. For implementation help, refer to eBay API documentation |
| advertisingEligibility.reason | string | No | The reason why a seller is ineligible for the specified eBay advertising program. This field is only returned if the seller is ineligible for the eBay advertising program. For implementation help, refer to eBay API documentation |
| advertisingEligibility.status | string | No | The seller eligibility status for the specified eBay advertising program. For implementation help, refer to eBay API documentation |
