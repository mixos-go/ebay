---
title: testSubscription
category: Notification_API
api_name: testSubscription
method: POST
path: /subscription/{subscription_id}/test
---

**Category:** Notification_API
**API:** testSubscription

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/test

## API Description
This method triggers a mocked test payload that includes a notification ID, publish date, and so on. Use this method to test your subscription end-to-end. You can create the subscription in disabled mode, test it using this method, and when everything is ready, you can enable the subscription (see the enableSubscription method). Note: Use the notificationId to tell the difference between a test payload and a real payload.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscription_id (path) | string | Yes | The unique identifier of the subscription to test. Use getSubscriptions to retrieve subscription IDs. |

## Response
_No documented response fields._
