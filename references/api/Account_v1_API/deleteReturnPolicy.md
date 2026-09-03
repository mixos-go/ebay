---
title: deleteReturnPolicy
category: Account_v1_API
api_name: deleteReturnPolicy
method: DELETE
path: /return_policy/{return_policy_id}
---

**Category:** Account_v1_API
**API:** deleteReturnPolicy

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/return_policy/{return_policy_id}

## API Description
This method deletes a return policy. Supply the ID of the policy you want to delete in the returnPolicyId path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| return_policy_id (path) | string | Yes | This path parameter specifies the unique identifier of the return policy you want to delete. This ID can be retrieved for a return policy by using the getReturnPolicies method. |

## Response
_No documented response fields._
