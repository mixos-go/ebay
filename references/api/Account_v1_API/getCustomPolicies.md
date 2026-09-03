---
title: getCustomPolicies
category: Account_v1_API
api_name: getCustomPolicies
method: GET
path: /custom_policy/
---

**Category:** Account_v1_API
**API:** getCustomPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/custom_policy/

## API Description
This method retrieves the list of custom policies defined for a seller's account. To limit the returned custom policies, specify the policy_types query parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| policy_types (query) | string | No | This query parameter specifies the type of custom policies to be returned. Multiple policy types may be requested in a single call by providing a comma-delimited set of all policy types to be returned. Note: Omitting this query parameter from a request will also return policies of all policy types.  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| customPolicies | array<CompactCustomPolicyResponse> | No | This array contains the custom policies that match the input criteria. |
| customPolicies.customPolicyId | string | No | The unique custom policy identifier for the policy being returned. Note: This value is automatically assigned by the system when the policy is created. |
| customPolicies.label | string | No | Customer-facing label shown on View Item pages for items to which the policy applies. This seller-defined string is displayed as a system-generated hyperlink pointing to the seller's policy information. Max length: 65 |
| customPolicies.name | string | No | The seller-defined name for the custom policy. Names must be unique for policies assigned to the same seller and policy type. Note: This field is visible only to the seller. Max length: 65 |
| customPolicies.policyType | string | No | Specifies the type of Custom Policy being returned. For implementation help, refer to eBay API documentation |
| href | string | No | This field is for future use. |
| limit | integer | No | This field is for future use. |
| next | string | No | This field is for future use. |
| offset | integer | No | This field is for future use. |
| prev | string | No | This field is for future use. |
| total | integer | No | This field is for future use. |
