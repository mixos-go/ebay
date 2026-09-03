---
title: createCustomerServiceMetricTask
category: Feed_API
api_name: createCustomerServiceMetricTask
method: POST
path: /customer_service_metric_task
---

**Category:** Feed_API
**API:** createCustomerServiceMetricTask

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/customer_service_metric_task

## API Description
Use this method to create a customer service metrics download task with filter criteria for the customer service metrics report. When using this method, specify the feedType and filterCriteria including both evaluationMarketplaceId and customerServiceMetricType for the report. The method returns the location response header containing the call URI to use with getCustomerServiceMetricTask to retrieve status and details on the task. Only CURRENT Customer Service Metrics reports can be generated with the Sell Feed API. PROJECTED reports are not supported at this time. See the getCustomerServiceMetric method document in the Analytics API for more information about these two types of reports. Note: Before calling this API, retrieve the summary of the seller's performance and rating for the customer service metric by calling getCustomerServiceMetric (part of the Analytics API ). You can then populate the create task request fields with the values from the response. This technique eliminates failed tasks that request a report for a customerServiceMetricType and evaluationMarketplaceId that are without evaluation.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | Yes | Use this header to specify the natural language in which the authenticated user desires the response. For example, en-US for English or de-DE for German. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType | string | No | The feedType specified for the customer service metric task being created. The report lists the transaction details that contribute to the service metrics evaluation. Supported types include: CUSTOMER_SERVICE_METRICS_REPORT |
| filterCriteria | CustomerServiceMetricsFilterCriteria | No | This container is used to customize and set criteria for Customer Service Metric report that will be associated with the task. |
| filterCriteria.customerServiceMetricType | string | No | An enumeration value that specifies the customer service metric that eBay tracks to measure seller performance. See CustomerServiceMetricTypeEnum for values. For implementation help, refer to eBay API documentation |
| filterCriteria.evaluationMarketplaceId | string | No | An enumeration value that specifies the eBay marketplace where the evaluation occurs. See MarketplaceIdEnum for values. For implementation help, refer to eBay API documentation |
| filterCriteria.listingCategories | array<string> | No | A list of listing category IDs on which the service metric is measured. A seller can use one or more L1 (top-level) eBay categories to get metrics specific to those L1 categories. The Category IDs for each L1 category are required. Category ID values for L1 categories can be retrieved using the Taxo |
| filterCriteria.shippingRegions | array<string> | No | A list of shipping region enumeration values on which the service metric is measured. This comma delimited array allows the seller to customize the report to focus on domestic or international shipping. Note: Pass this attribute to narrow down your filter results for the ITEM_NOT_RECEIVED customerSe |
| schemaVersion | string | No | The version number of the customer service metric. Note: This field must have a value of 1.0 . |

## Response
_No documented response fields._
