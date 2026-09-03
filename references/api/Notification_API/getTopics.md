---
title: getTopics
category: Notification_API
api_name: getTopics
method: GET
path: /topic
---

**Category:** Notification_API
**API:** getTopics

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/topic

## API Description
This method returns a paginated collection of all supported topics, along with the details for the topics. This information includes supported schema versions, formats, and other metadata for the topics. Applications can subscribe to any of the topics for a supported schema version and format, limited by the authorization scopes required to subscribe to the topic. A topic specifies the type of information to be received and the data types associated with an event. An event occurs in the eBay system, such as when a user requests deletion or revokes access for an application. An event is an instance of an event type (topic).

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| continuation_token (query) | string | No | This string value can be used to return the next page in the result set. The string to use here is returned in the next field of the current page of results. |
| limit (query) | string | No | The maximum number of notification topics to return per page from the result set. Min: 10 Max: 100 Default: 20 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of items to return per page, from the result set. A result set is the complete set of results returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter defau |
| next | string | No | The URL to access the next set of results. This field includes a continuation_token . No prev field is returned, but this value is persistent during the session so that you can use it to return to the next page. This field is not returned if fewer records than specified by the limit field are return |
| topics | array<Topic> | No | An array of topics that match the specified criteria. |
| topics.authorizationScopes | array<string> | No | The authorization scopes required to subscribe to this topic. |
| topics.context | string | No | The business context associated with this topic. For implementation help, refer to eBay API documentation |
| topics.description | string | No | The description of the topic. |
| topics.filterable | boolean | No | The indicator of whether this topic is filterable or not. |
| topics.scope | string | No | The scope of this topic. For implementation help, refer to eBay API documentation |
| topics.status | string | No | The status of this topic. For implementation help, refer to eBay API documentation |
| topics.supportedPayloads | array<PayloadDetail> | No | The supported payloads for this topic. |
| topics.supportedPayloads.deliveryProtocol | string | No | The supported delivery protocols. For implementation help, refer to eBay API documentation |
| topics.supportedPayloads.deprecated | boolean | No | A deprecation indicator. |
| topics.supportedPayloads.format | array<string> | No | The supported format. Presently, JSON is the only supported format. |
| topics.supportedPayloads.schemaVersion | string | No | The supported schema version. |
| topics.topicId | string | No | The unique identifier for the topic. |
| total | integer | No | The total number of matches for the search criteria. |
