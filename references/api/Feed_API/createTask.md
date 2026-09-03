---
title: createTask
category: Feed_API
api_name: createTask
method: POST
path: /task
---

**Category:** Feed_API
**API:** createTask

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/task

## API Description
This method creates an upload task or a download task without filter criteria. When using this method, specify the feedType and the feed file schemaVersion . The feed type specified sets the task as a download or an upload task. For details about the upload and download flows, see Working with Order Feeds in the Selling Integration Guide. Note: The scope depends on the feed type. An error message results when an unsupported scope or feed type is specified. The following list contains this method's authorization scopes and their corresponding feed types: https://api.ebay.com/oauth/api_scope/sell.inventory: See LMS FeedTypes https://api.ebay.com/oauth/api_scope/sell.fulfillment: LMS_ORDER_ACK (specify for upload tasks). Also see LMS FeedTypes https://api.ebay.com/oauth/api_scope/sell.marketing: None* https://api.ebay.com/oauth/api_scope/commerce.catalog.readonly: None* * Reserved for future release

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the item is hosted. For example: X-EBAY-C-MARKETPLACE-ID:EBAY_US This identifies the eBay marketplace that applies to this task. See MarketplaceIdEnum for supported values. Note: When listing the items in the feed file on the French Canada and French Belgium mark |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |
| Accept-Language (header) | string | No | The Accept-Language header is required for listing items in the French Canada and French Belgium marketplaces. Set the following headers to list items on these marketplaces: French Canada : Set the X-EBAY-C-MARKETPLACE-ID header value to EBAY_CA and include the Accept-Language header with a value of |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The feed type associated with the task. Available feed types: Inventory upload feed types Fulfillment upload feed types Seller Hub feed types |
| schemaVersion | string | No | The schemaVersion/version number of the file format: Version Details / Schema Version Seller Hub feed schema version |

## Response
_No documented response fields._
