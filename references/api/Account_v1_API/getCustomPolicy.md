---
title: getCustomPolicy
category: Account_v1_API
api_name: getCustomPolicy
method: GET
path: /custom_policy/{custom_policy_id}
---

**Category:** Account_v1_API
**API:** getCustomPolicy

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/custom_policy/{custom_policy_id}

## API Description
This method retrieves the custom policy specified by the custom_policy_id path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| custom_policy_id (path) | string | Yes | This path parameter is the unique identifier of the custom policy to retrieve. This ID can be retrieved for a custom policy by using the getCustomPolicies method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| customPolicyId | string | No | The unique custom policy identifier for a policy. |
| description | string | No | Contains the seller's policy and policy terms. Buyers access this information from the View Item page for items to which the policy has been applied. Max length: 15,000 |
| label | string | No | Customer-facing label shown on View Item pages for items to which the policy applies. This seller-defined string is displayed as a system-generated hyperlink pointing to the seller's policy information. Max length: 65 |
| name | string | No | The seller-defined name for the custom policy. Names must be unique for policies assigned to the same seller and policy type. Note: This field is visible only to the seller. Max length: 65 |
| policyType | string | No | Specifies the type of Custom Policy being returned. For implementation help, refer to eBay API documentation |
