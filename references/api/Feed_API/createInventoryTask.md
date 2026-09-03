---
title: createInventoryTask
category: Feed_API
api_name: createInventoryTask
method: POST
path: /inventory_task
---

**Category:** Feed_API
**API:** createInventoryTask

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/inventory_task

## API Description
This method creates an inventory-related download task for a specified feed type with optional filter criteria. When using this method, specify the feedType . This method returns the location response header containing the getInventoryTask call URI to retrieve the inventory task you just created. The URL includes the eBay-assigned task ID, which you can use to reference the inventory task. To retrieve the status of the task, use the getInventoryTask method to retrieve a single task ID or the getInventoryTasks method to retrieve multiple task IDs. Note: The scope depends on the feed type. An error message results when an unsupported scope or feed type is specified. Presently, this method supports Active Inventory Report. The ActiveInventoryReport returns a report that contains price and quantity information for all of the active listings for a specific seller. A seller can use this information to maintain their inventory on eBay.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The feed type associated with the inventory task you are about to create. Presently, only one feed type is available: LMS_ACTIVE_INVENTORY_REPORT See Report download feed types for more information. |
| filterCriteria | InventoryFilterCriteria | No | This container allows a seller to create an ActiveInventoryReport for a single listing format. |
| filterCriteria.listingFormat | string | No | The listing format for the ActiveInventoryReport being created. Supported types are: AUCTION FIXED_PRICE For implementation help, refer to eBay API documentation |
| schemaVersion | string | No | The version number of the inventory task to use for the feedType . Note: This field must have a value of 1.0 . |

## Response
_No documented response fields._
