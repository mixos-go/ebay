---
title: updateConfig
category: Notification_API
api_name: updateConfig
method: PUT
path: /config
---

**Category:** Notification_API
**API:** updateConfig

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/config

## API Description
This method allows applications to create a new configuration or update an existing configuration. This app-level configuration allows developers to set up alerts.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| alertEmail | string | No | This field is used to add or modify an email address that will be used for Notification API alerts associated with the application. getConfig can be used to get the email address currently being used for alerts. |

## Response
_No documented response fields._
