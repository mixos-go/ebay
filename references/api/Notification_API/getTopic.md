---
title: getTopic
category: Notification_API
api_name: getTopic
method: GET
path: /topic/{topic_id}
---

**Category:** Notification_API
**API:** getTopic

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/topic/{topic_id}

## API Description
This method allows applications to retrieve details for the specified topic. This information includes supported schema versions, formats, and other metadata for the topic. Applications can subscribe to any of the topics for a supported schema version and format, limited by the authorization scopes required to subscribe to the topic. A topic specifies the type of information to be received and the data types associated with an event. An event occurs in the eBay system, such as when a user requests deletion or revokes access for an application. An event is an instance of an event type (topic). Specify the topic to retrieve using the topic_id URI parameter. Note: Use the getTopics method to find a topic if you do not know the topic ID.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| topic_id (path) | string | Yes | The unique identifier of the notification topic for which the details are retrieved. Use getTopics to retrieve the topic ID. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| authorizationScopes | array<string> | No | The authorization scopes required to subscribe to this topic. |
| context | string | No | The business context associated with this topic. For implementation help, refer to eBay API documentation |
| description | string | No | The description of the topic. |
| filterable | boolean | No | The indicator of whether this topic is filterable or not. |
| scope | string | No | The scope of this topic. For implementation help, refer to eBay API documentation |
| status | string | No | The status of this topic. For implementation help, refer to eBay API documentation |
| supportedPayloads | array<PayloadDetail> | No | The supported payloads for this topic. |
| supportedPayloads.deliveryProtocol | string | No | The supported delivery protocols. For implementation help, refer to eBay API documentation |
| supportedPayloads.deprecated | boolean | No | A deprecation indicator. |
| supportedPayloads.format | array<string> | No | The supported format. Presently, JSON is the only supported format. |
| supportedPayloads.schemaVersion | string | No | The supported schema version. |
| topicId | string | No | The unique identifier for the topic. |
