---
title: getStore
category: Store_API
api_name: getStore
method: GET
path: /store
---

**Category:** Store_API
**API:** getStore

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/store

## API Description
This method is used to retrieve information for an eBay user's store such as store name, store URL, and description.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| description | string | No | The seller-provided description of the eBay Store. Max length: 300 |
| lastOpenedTime | string | No | Indicates the time the store was last opened or reopened. |
| logo | StoreLogoType | No | This container provides information about a Store logo. |
| logo.url | string | No | The URL of the seller's store logo. |
| name | string | No | The name of the eBay Store. The name is shown at the top of the Store page. Max length: 35 |
| url | string | No | The complete URL of the user's store. |
| urlPath | string | No | The relative URL path of the Store. Max length: 58 |
