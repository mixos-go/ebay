---
title: getSubscriptionFilter
category: Notification_API
api_name: getSubscriptionFilter
method: GET
path: /subscription/{subscription_id}/filter/{filter_id}
---

**Category:** Notification_API
**API:** getSubscriptionFilter

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/filter/{filter_id}

## API Description
This method allows applications to retrieve the filter details for the specified subscription filter. Specify the subscription filter to retrieve by using the subscription_id and the filter_id associated with the subscription filter. The filter_id can be found in the response body for the getSubscription method, if there is a filter applied on the subscription. Filters allow applications to only be sent notifications that match a provided criteria. Notifications that do not match this criteria will not be sent to the destination.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter_id (path) | string | Yes | The unique identifier of the subscription filter. Filter ID values, if configured for a subscription, will be shown in the subscriptions.filterId field in getSubscription and getSubscription responses. The filter ID value is also returned in the Location response header when a filter is created with |
| subscription_id (path) | string | Yes | The unique identifier of the subscription associated with the filter. Use getSubscriptions to retrieve subscription IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| creationDate | string | No | The creation date for this subscription filter. |
| filterId | string | No | The unique identifier for this subscription filter. |
| filterSchema | object | No | The content of this subscription filter as a valid JSON Schema Core document (version 2020-12 or later). The filterSchema provided must describe the subscription's notification payload such that it supplies valid criteria to filter the subscription's notifications. |
| filterStatus | string | No | The status of this subscription filter. For implementation help, refer to eBay API documentation |
| subscriptionId | string | No | The unique identifier for the subscription. |
