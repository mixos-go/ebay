---
title: createSubscription
category: Notification_API
api_name: createSubscription
method: POST
path: /subscription
---

**Category:** Notification_API
**API:** createSubscription

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/subscription

## API Description
This method allows applications to create a subscription for a topic and supported schema version. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business. Each application and topic-schema pairing to a subscription should have a 1:1 cardinality. You can create the subscription in disabled mode, test it (see the test method), and when everything is ready, you can enable the subscription (see the enableSubscription method). Note: If an application is not authorized to subscribe to a topic, for example, if your authorization does not include the list of scopes required for the topic, an error code of 195011 is returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| destinationId | string | No | The unique identifier of the destination endpoint that will receive notifications associated with this subscription. Use the getDestinations method to retrieve destination IDs. |
| payload | SubscriptionPayloadDetail | No | The payload associated with the notification topic. Use getTopics or getTopic to get the supported payload for the topic. |
| payload.deliveryProtocol | string | No | The supported delivery protocol of the notification topic. Note: HTTPS is currently the only supported delivery protocol of all notification topics. For implementation help, refer to eBay API documentation |
| payload.format | string | No | The supported data format of the payload. Note: JSON is currently the only supported format for all notification topics. For implementation help, refer to eBay API documentation |
| payload.schemaVersion | string | No | The supported schema version for the notification topic. See the supportedPayloads.schemaVersion field for the topic in getTopics or getTopic response. |
| status | string | No | Set the status of the subscription to ENABLED or DISABLED . For implementation help, refer to eBay API documentation |
| topicId | string | No | The unique identifier of the notification topic to subscribe to. Use getTopics to get topic IDs. |

## Response
_No documented response fields._
