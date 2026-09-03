---
title: getSubscription
category: Notification_API
api_name: getSubscription
method: GET
path: /subscription/{subscription_id}
---

**Category:** Notification_API
**API:** getSubscription

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}

## API Description
This method allows applications to retrieve subscription details for the specified subscription. Specify the subscription to retrieve using the subscription_id . Use the getSubscriptions method to browse all subscriptions if you do not know the subscription_id . Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscription_id (path) | string | Yes | The unique identifier of the subscription to retrieve. Use getSubscriptions to retrieve subscription IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| creationDate | string | No | The creation date for this subscription. |
| destinationId | string | No | The unique identifier for the destination associated with this subscription. |
| filterId | string | No | The unique identifier for the filter associated with this subscription. |
| payload | SubscriptionPayloadDetail | No | The payload associated with this subscription. |
| payload.deliveryProtocol | string | No | The supported delivery protocol of the notification topic. Note: HTTPS is currently the only supported delivery protocol of all notification topics. For implementation help, refer to eBay API documentation |
| payload.format | string | No | The supported data format of the payload. Note: JSON is currently the only supported format for all notification topics. For implementation help, refer to eBay API documentation |
| payload.schemaVersion | string | No | The supported schema version for the notification topic. See the supportedPayloads.schemaVersion field for the topic in getTopics or getTopic response. |
| status | string | No | The status of this subscription. For implementation help, refer to eBay API documentation |
| subscriptionId | string | No | The unique identifier for the subscription. |
| topicId | string | No | The unique identifier for the topic associated with this subscription. |
