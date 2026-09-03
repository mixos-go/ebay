---
title: getConfig
category: Notification_API
api_name: getConfig
method: GET
path: /config
---

**Category:** Notification_API
**API:** getConfig

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/config

## API Description
This method allows applications to retrieve a previously created configuration.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| alertEmail | string | No | This field is used to add or modify an email address that will be used for Notification API alerts associated with the application. getConfig can be used to get the email address currently being used for alerts. |
