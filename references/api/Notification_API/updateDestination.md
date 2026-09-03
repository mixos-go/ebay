---
title: updateDestination
category: Notification_API
api_name: updateDestination
method: PUT
path: /destination/{destination_id}
---

**Category:** Notification_API
**API:** updateDestination

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/destination/{destination_id}

## API Description
This method allows applications to update a destination. Note: The destination should be created and ready to respond with the expected challengeResponse for the endpoint to be registered successfully. Refer to the Notification API overview for more information.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| destination_id (path) | string | Yes | The unique identifier for the destination. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| deliveryConfig | DeliveryConfig | No | This container is used to specify the destination endpoint and verification token associated with this endpoint. |
| deliveryConfig.endpoint | string | No | The endpoint for this destination. Note: The provided endpoint URL should use the HTTPS protocol, and it should not contain an internal IP address or localhost in its path. |
| deliveryConfig.verificationToken | string | No | The verification token associated with this endpoint. Note: The provided verification token must be between 32 and 80 characters. Allowed characters include alphanumeric characters, underscores ( _ ), and hyphens ( - ); no other characters are allowed. |
| name | string | No | The seller-specified name for the destination endpoint. |
| status | string | No | This field sets the status for the destination endpoint as ENABLED or DISABLED . Note: The MARKED_DOWN value is set by eBay systems and cannot be used in a create or update call by applications. For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
