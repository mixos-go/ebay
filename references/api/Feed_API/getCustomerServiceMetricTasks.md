---
title: getCustomerServiceMetricTasks
category: Feed_API
api_name: getCustomerServiceMetricTasks
method: GET
path: /customer_service_metric_task
---

**Category:** Feed_API
**API:** getCustomerServiceMetricTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/customer_service_metric_task

## API Description
Use this method to return an array of customer service metric tasks. You can limit the tasks returned by specifying a date range. Note: You can pass in either the look_back_days or date_range , but not both.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| date_range (query) | string | No | The task creation date range. The results are filtered to include only tasks with a creation date that is equal to the dates specified or is within the specified range. Do not use with the look_back_days parameter. Format: UTC For example, tasks within a range: yyyy-MM-ddThh:mm:ss.SSSZ..yyyy-MM-ddTh |
| feed_type (query) | string | No | The feed type associated with the tasks being retrieved. The only presently supported value is CUSTOMER_SERVICE_METRICS_REPORT . |
| limit (query) | string | No | The number of customer service metric tasks to return per page of the result set. Use this parameter in conjunction with the offset parameter to control the pagination of the output. For example, if offset is set to 10 and limit is set to 10, the call retrieves tasks 11 thru 20 from the result set.  |
| look_back_days (query) | string | No | The number of previous days in which to search for tasks. Do not use with the date_range parameter. If both date_range and look_back_days are omitted, this parameter's default value is used. Default value: 7 Range: 1-90 (inclusive) |
| offset (query) | string | No | The number of customer service metric tasks to skip in the result set before returning the first task in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page o |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request, which is the maximum number of tasks to return per page, from the result set. A result set is the complete set of tasks returned by the method. Note: Even though this parameter is not required to be submitted in the request, the parameter de |
| next | string | No | The relative path to the call URI for the next page of results. This value is returned if there is an additional page of results to return from the result set. |
| offset | integer | No | The number of results skipped in the result set before returning the first result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the previous page of results. This parameter is returned if a previous page of results from the result set exists. |
| tasks | array<ServiceMetricsTask> | No | An array of the customer service tasks on this page. The tasks are sorted by creation date. An empty array is returned if the filter criteria excludes all tasks. |
| tasks.completionDate | string | No | The timestamp when the customer service metrics task went into the COMPLETED or COMPLETED_WITH_ERROR state. This field is only returned if the status is one of the two completed values. This state means that eBay has compiled the report for the seller based on the seller’s filter criteria, and the s |
| tasks.creationDate | string | No | The date the customer service metrics task was created. |
| tasks.detailHref | string | No | The relative getCustomerServiceMetricTask call URI path to retrieve the corresponding task. |
| tasks.feedType | string | No | The feed type associated with the task. |
| tasks.filterCriteria | CustomerServiceMetricsFilterCriteria | No | This container shows the criteria set for the report. |
| tasks.filterCriteria.customerServiceMetricType | string | No | An enumeration value that specifies the customer service metric that eBay tracks to measure seller performance. See CustomerServiceMetricTypeEnum for values. For implementation help, refer to eBay API documentation |
| tasks.filterCriteria.evaluationMarketplaceId | string | No | An enumeration value that specifies the eBay marketplace where the evaluation occurs. See MarketplaceIdEnum for values. For implementation help, refer to eBay API documentation |
| tasks.filterCriteria.listingCategories | array<string> | No | A list of listing category IDs on which the service metric is measured. A seller can use one or more L1 (top-level) eBay categories to get metrics specific to those L1 categories. The Category IDs for each L1 category are required. Category ID values for L1 categories can be retrieved using the Taxo |
| tasks.filterCriteria.shippingRegions | array<string> | No | A list of shipping region enumeration values on which the service metric is measured. This comma delimited array allows the seller to customize the report to focus on domestic or international shipping. Note: Pass this attribute to narrow down your filter results for the ITEM_NOT_RECEIVED customerSe |
| tasks.schemaVersion | string | No | The schema version number of the file format. If omitted, the default value is used. Default value: 1.0 |
| tasks.status | string | No | An enumeration value that indicates the state of the task. See FeedStatusEnum for values. For implementation help, refer to eBay API documentation |
| tasks.taskId | string | No | The unique eBay-assigned ID of the task. |
| total | integer | No | The total number of tasks that match the criteria. |
