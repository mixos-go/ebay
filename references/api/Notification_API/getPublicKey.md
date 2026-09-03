---
title: getPublicKey
category: Notification_API
api_name: getPublicKey
method: GET
path: /public_key/{public_key_id}
---

**Category:** Notification_API
**API:** getPublicKey

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/public_key/{public_key_id}

## API Description
This method allows users to retrieve a public key using a specified key ID. The public key that is returned in the response payload is used to process and validate eBay notifications. The public key ID, which is a required request parameter for this method, is retrieved from the Base64-encoded X-EBAY-SIGNATURE header that is included in the eBay notification. Important! The retrieved public key value should be cached for a temporary — but reasonable — amount of time (e.g., one-hour is recommended.) This key should not be requested for every notification since doing so can result in exceeding API call limits if a large number of notification requests is received. Note: For more details about how to process eBay push notifications and validate notification message payloads, see the Notification API overview .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| public_key_id (path) | string | Yes | The unique key ID that is used to retrieve the public key. Note: This is retrieved from the X-EBAY-SIGNATURE header that is included with the push notification. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| algorithm | string | No | The algorithm associated with the public key that is returned, such as Elliptic Curve Digital Signature Algorithm (ECDSA). |
| digest | string | No | The digest associated with the public key that is returned, such as Secure Hash Algorithm 1 (SHA1). |
| key | string | No | The public key that is returned for the specified key ID. This value is used to validate the eBay push notification message payload. |
