---
title: deletePaymentPolicy
category: Account_v1_API
api_name: deletePaymentPolicy
method: DELETE
path: /payment_policy/{payment_policy_id}
---

**Category:** Account_v1_API
**API:** deletePaymentPolicy

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/payment_policy/{payment_policy_id}

## API Description
This method deletes a payment policy. Supply the ID of the policy you want to delete in the paymentPolicyId path parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_policy_id (path) | string | Yes | This path parameter specifies the unique identifier of the payment policy you want to delete. This ID can be retrieved for a payment policy by using the getPaymentPolices method. |

## Response
_No documented response fields._
