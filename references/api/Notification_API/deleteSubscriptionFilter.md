---
title: deleteSubscriptionFilter
category: Notification_API
api_name: deleteSubscriptionFilter
method: DELETE
path: /subscription/{subscription_id}/filter/{filter_id}
---

**Category:** Notification_API
**API:** deleteSubscriptionFilter

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/filter/{filter_id}

## API Description
This method allows applications to disable the active filter on a subscription, so that a new subscription filter may be added. Note: Subscription filters in PENDING status can not be disabled. However, a new filter can be created instead with the createSubscriptionFilter method and this new filter will override the PENDING filter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter_id (path) | string | Yes | The unique identifier of the subscription filter to delete. Filter ID values, if configured for a subscription, will be shown in the subscriptions.filterId field in getSubscription and getSubscription responses. The filter ID value is also returned in the Location response header when a filter is cr |
| subscription_id (path) | string | Yes | The unique identifier of the subscription associated with the filter to delete. Use getSubscriptions to retrieve subscription IDs. |

## Response
_No documented response fields._
