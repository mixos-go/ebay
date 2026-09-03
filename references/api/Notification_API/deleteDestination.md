---
title: deleteDestination
category: Notification_API
api_name: deleteDestination
method: DELETE
path: /destination/{destination_id}
---

**Category:** Notification_API
**API:** deleteDestination

**Method:** DELETE
**HTTP Path:** https://api.ebay.com{basePath}/destination/{destination_id}

## API Description
This method provides applications a way to delete a destination. The same destination ID can be used by many destinations. Trying to delete an active destination results in an error. You can disable a subscription, and when the destination is no longer in use, you can delete it.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| destination_id (path) | string | Yes | The unique identifier of the destination to delete. Only disabled or marked down destinations can be deleted, and enabled destinations cannot be deleted. Use getDestination or getDestinations to see the current status of a destination. |

## Response
_No documented response fields._
