---
title: getDestination
category: Notification_API
api_name: getDestination
method: GET
path: /destination/{destination_id}
---

**Category:** Notification_API
**API:** getDestination

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/destination/{destination_id}

## API Description
This method allows applications to fetch the details for a destination. The details include the destination name, status, and configuration, including the endpoint and verification token.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| destination_id (path) | string | Yes | The unique identifier of the destination to retrieve. Use getDestinations to retrieve destination IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| deliveryConfig | DeliveryConfig | No | The configuration associated with this destination. |
| deliveryConfig.endpoint | string | No | The endpoint for this destination. Note: The provided endpoint URL should use the HTTPS protocol, and it should not contain an internal IP address or localhost in its path. |
| deliveryConfig.verificationToken | string | No | The verification token associated with this endpoint. Note: The provided verification token must be between 32 and 80 characters. Allowed characters include alphanumeric characters, underscores ( _ ), and hyphens ( - ); no other characters are allowed. |
| destinationId | string | No | The unique identifier for the destination. |
| name | string | No | The name associated with this destination. |
| status | string | No | The status for this destination. Note: The MARKED_DOWN value is set by eBay systems and cannot be used in a create or update call by applications. Valid values: ENABLED DISABLED MARKED_DOWN For implementation help, refer to eBay API documentation |
