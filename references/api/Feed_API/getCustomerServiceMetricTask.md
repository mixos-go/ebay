---
title: getCustomerServiceMetricTask
category: Feed_API
api_name: getCustomerServiceMetricTask
method: GET
path: /customer_service_metric_task/{task_id}
---

**Category:** Feed_API
**API:** getCustomerServiceMetricTask

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/customer_service_metric_task/{task_id}

## API Description
Use this method to retrieve customer service metric task details for the specified task. The input is task_id .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| task_id (path) | string | Yes | This path parameter is the unique identifier of the customer service metric task being retrieved. Use the getCustomerServiceMetricTasks method to retrieve task IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| completionDate | string | No | The timestamp when the customer service metrics task went into the COMPLETED or COMPLETED_WITH_ERROR state. This field is only returned if the status is one of the two completed values. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the s |
| creationDate | string | No | The date the customer service metrics task was created. |
| detailHref | string | No | The relative getCustomerServiceMetricTask call URI path to retrieve the corresponding task. |
| feedType | string | No | The feed type associated with the task. |
| filterCriteria | CustomerServiceMetricsFilterCriteria | No | This container shows the criteria set for the report. |
| filterCriteria.customerServiceMetricType | string | No | An enumeration value that specifies the customer service metric that eBay tracks to measure seller performance. See CustomerServiceMetricTypeEnum for values. For implementation help, refer to eBay API documentation |
| filterCriteria.evaluationMarketplaceId | string | No | An enumeration value that specifies the eBay marketplace where the evaluation occurs. See MarketplaceIdEnum for values. For implementation help, refer to eBay API documentation |
| filterCriteria.listingCategories | array<string> | No | A list of listing category IDs on which the service metric is measured. A seller can use one or more L1 (top-level) eBay categories to get metrics specific to those L1 categories. The Category IDs for each L1 category are required. Category ID values for L1 categories can be retrieved using the Taxo |
| filterCriteria.shippingRegions | array<string> | No | A list of shipping region enumeration values on which the service metric is measured. This comma delimited array allows the seller to customize the report to focus on domestic or international shipping. Note: Pass this attribute to narrow down your filter results for the ITEM_NOT_RECEIVED customerSe |
| schemaVersion | string | No | The schema version number of the file format. If omitted, the default value is used. Default value: 1.0 |
| status | string | No | An enumeration value that indicates the state of the task. See FeedStatusEnum for values. For implementation help, refer to eBay API documentation |
| taskId | string | No | The unique eBay-assigned ID of the task. |
