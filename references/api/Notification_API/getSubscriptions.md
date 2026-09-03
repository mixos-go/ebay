---
title: getSubscriptions
category: Notification_API
api_name: getSubscriptions
method: GET
path: /subscription
---

**Category:** Notification_API
**API:** getSubscriptions

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/subscription

## API Description
This method allows applications to retrieve a list of all subscriptions. The list returned is a paginated collection of subscription resources. Subscriptions allow applications to express interest in notifications and keep receiving the information relevant to their business.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| continuation_token (query) | string | No | This string value can be used to return the next page in the result set. The string to use here is returned in the next field of the current page of results. |
| limit (query) | string | No | The maximum number of subscriptions to return per page from the result set. Min: 10 Max: 100 Default: 20 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of items to return per page, from the result set. A result set is the complete set of results returned by the method. Note: Though this parameter is not required to be submitted in the request, the parameter defau |
| next | string | No | The URL to access the next set of results. This field includes a continuation_token . No prev field is returned, but this value is persistent during the session so that you can use it to return to the next page. This field is not returned if fewer records than specified by the limit field are return |
| subscriptions | array<Subscription> | No | The subscriptions that match the search criteria. |
| subscriptions.creationDate | string | No | The creation date for this subscription. |
| subscriptions.destinationId | string | No | The unique identifier for the destination associated with this subscription. |
| subscriptions.filterId | string | No | The unique identifier for the filter associated with this subscription. |
| subscriptions.payload | SubscriptionPayloadDetail | No | The payload associated with this subscription. |
| subscriptions.payload.deliveryProtocol | string | No | The supported delivery protocol of the notification topic. Note: HTTPS is currently the only supported delivery protocol of all notification topics. For implementation help, refer to eBay API documentation |
| subscriptions.payload.format | string | No | The supported data format of the payload. Note: JSON is currently the only supported format for all notification topics. For implementation help, refer to eBay API documentation |
| subscriptions.payload.schemaVersion | string | No | The supported schema version for the notification topic. See the supportedPayloads.schemaVersion field for the topic in getTopics or getTopic response. |
| subscriptions.status | string | No | The status of this subscription. For implementation help, refer to eBay API documentation |
| subscriptions.subscriptionId | string | No | The unique identifier for the subscription. |
| subscriptions.topicId | string | No | The unique identifier for the topic associated with this subscription. |
| total | integer | No | The total number of matches for the search criteria. |
