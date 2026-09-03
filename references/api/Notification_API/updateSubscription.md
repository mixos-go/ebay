---
title: updateSubscription
category: Notification_API
api_name: updateSubscription
method: PUT
path: /subscription/{subscription_id}
---

**Category:** Notification_API
**API:** updateSubscription

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}

## API Description
This method allows applications to update a subscription. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business. Note: This call returns an error if an application is not authorized to subscribe to a topic. You can pause and restart a subscription. See the disableSubscription and enableSubscription methods.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| subscription_id (path) | string | Yes | The unique identifier for the subscription to update. Use getSubscriptions to retrieve subscription IDs. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| destinationId | string | No | The unique identifier of the destination endpoint that will receive notifications associated with this subscription. Use getDestinations to retrieve destination IDs. |
| payload | SubscriptionPayloadDetail | No | The payload associated with this subscription. |
| payload.deliveryProtocol | string | No | The supported delivery protocol of the notification topic. Note: HTTPS is currently the only supported delivery protocol of all notification topics. For implementation help, refer to eBay API documentation |
| payload.format | string | No | The supported data format of the payload. Note: JSON is currently the only supported format for all notification topics. For implementation help, refer to eBay API documentation |
| payload.schemaVersion | string | No | The supported schema version for the notification topic. See the supportedPayloads.schemaVersion field for the topic in getTopics or getTopic response. |
| status | string | No | Set the status of the subscription being updated to ENABLED or DISABLED. For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
