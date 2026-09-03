---
title: enableSubscription
category: Notification_API
api_name: enableSubscription
method: POST
path: /subscription/{subscription_id}/enable
---

**Category:** Notification_API
**API:** enableSubscription

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/enable

## API Description
This method allows applications to enable a disabled subscription. To pause (or disable) an enabled subscription, call disableSubscription .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscription_id (path) | string | Yes | The unique identifier of a disabled subscription that will be enabled. Use getSubscriptions to retrieve subscription IDs. |

## Response
_No documented response fields._
