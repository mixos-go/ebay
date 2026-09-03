---
title: deleteSubscription
category: Notification_API
api_name: deleteSubscription
method: DELETE
path: /subscription/{subscription_id}
---

**Category:** Notification_API
**API:** deleteSubscription

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}

## API Description
This method allows applications to delete a subscription. Subscriptions can be deleted regardless of status.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscription_id (path) | string | Yes | The unique identifier of the subscription to delete. Use getSubscriptions to retrieve subscription IDs. |

## Response
_No documented response fields._
