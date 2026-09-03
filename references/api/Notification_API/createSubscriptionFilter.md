---
title: createSubscriptionFilter
category: Notification_API
api_name: createSubscriptionFilter
method: POST
path: /subscription/{subscription_id}/filter
---

**Category:** Notification_API
**API:** createSubscriptionFilter

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/subscription/{subscription_id}/filter

## API Description
This method allows applications to create a filter for a subscription. Filters allow applications to only be sent notifications that match a provided criteria. Notifications that do not match this criteria will not be sent to the destination. The filterSchema value must be a valid JSON Schema Core document (version 2020-12 or later). The filterSchema provided must describe the subscription's notification payload such that it supplies valid criteria to filter the subscription's notifications. The user does not need to provide $schema and $id definitions. When a filter is first created, it is not immediately active on the subscription. If the request has a valid JSON body, the successful call returns the HTTP status code 201&nbsp;Created . Newly created filters are in PENDING status until they are reviewed. If a filter is valid, it will move from PENDING status to ENABLED status. You can find the status of a filter using the getSubscriptionFilter method. See Creating a subscription filter for a topic for additional information. Note: Only one filter can be in ENABLED (which means active) status on a subscription at a time. If an ENABLED filter is overwritten by a new call to CREATE a filter for the subscription, it stays in ENABLED status until the new PENDING filter becomes the ENABLED filter, and the existing filter then becomes DISABLED .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| subscription_id (path) | string | Yes | The unique identifier of the subscription for which a filter will be created. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filterSchema | object | No | The content of a subscription filter as a valid JSON Schema Core document (version 2020-12 or later). The filterSchema provided must describe the subscription's notification payload such that it supplies valid criteria to filter the subscription's notifications. Note: Not all topics can have filters |

## Response
_No documented response fields._
