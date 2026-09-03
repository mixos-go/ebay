---
title: disableSubscription
category: Notification_API
api_name: disableSubscription
method: POST
path: /subscription/{subscription_id}/disable
---

**Category:** Notification_API
**API:** disableSubscription

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/disable

## API Description
This method disables a subscription, which prevents the subscription from providing notifications. To restart a subscription, call enableSubscription .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscription_id (path) | string | Yes | The unique identifier of an enabled subscription that will be disabled. Use getSubscriptions to retrieve subscription IDs. |

## Response
_No documented response fields._
