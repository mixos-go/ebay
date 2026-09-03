---
title: getReportTasks
category: Marketing_API
api_name: getReportTasks
method: GET
path: /ad_report_task
---

**Category:** Marketing_API
**API:** getReportTasks

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_report_task

## API Description
This method returns information on all the existing report tasks related to a seller. Use the report_task_statuses query parameter to control which reports to return. You can paginate the result set by specifying a limit , which dictates how many report tasks to return on each page of the response. Use the offset parameter to specify how many reports to skip in the result set before returning the first result. Important! For ad_report and ad_report_task methods, the API call limit is subject to a per user quota. These API calls can only be executed a maximum of 200 times per hour for each seller/user. If the number of calls per hour exceeds this limit, any new calls will be blocked for the next hour.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | Specifies the maximum number of report tasks to return on a page in the paginated response. Default: 10 Maximum: 500 |
| offset (query) | string | No | Specifies the number of report tasks to skip in the result set before returning the first report in the paginated response. Combine offset with the limit query parameter to control the reports returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the response contai |
| report_task_statuses (query) | string | No | This query parameter filters the returned report tasks by their status. Supply a comma-separated list of the report statuses you want returned. The results are filtered to include only the report statuses you specify. Note: The results might not include some report tasks if other search conditions e |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length : 2048 |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0 . |
| reportTasks | array<ReportTask> | No | A list of report tasks contained on this page from the paginated response. |
| reportTasks.campaignIds | array<string> | No | A list of IDs for the campaigns that are included in the report. A campaign ID is a unique eBay-assigned identifier of the campaign that's generated when the campaign is created. Call getCampaigns to return the current campaign IDs for a seller. |
| reportTasks.channels | array<string> | No | The channel for the advertising campaign that will be included in the report task. This value indicates whether the data included in the report task is for an Onsite or Offsite advertising campaign. |
| reportTasks.dateFrom | string | No | The date defining the start of the timespan covered by the report, formatted as an ISO 8601 timestamp. |
| reportTasks.dateTo | string | No | The date defining the end of the timespan covered by the report, formatted as an ISO 8601 timestamp. |
| reportTasks.dimensions | array<Dimension> | No | A list containing the dimension in the report. |
| reportTasks.dimensions.annotationKeys | array<string> | No | A list of annotations associated with the dimension of the report. |
| reportTasks.dimensions.dimensionKey | string | No | The name of the dimension on which the report is based. A dimension is an attribute to which the report data applies. |
| reportTasks.fundingModels | array<string> | No | The funding model for the campaign that shall be included in the report. Note: The default funding model for Promoted Listings reports is COST_PER_SALE . Valid Values: COST_PER_SALE COST_PER_CLICK |
| reportTasks.inventoryReferences | array<InventoryReference> | No | If supplied in the request, this field returns a list of the seller's inventory reference IDs included in the report. Each item is referenced by a pair of inventoryRefernceID and inventoryReferenceType values, where an inventory reference ID can be either a seller-defined SKU value or an inventoryIt |
| reportTasks.inventoryReferences.inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| reportTasks.inventoryReferences.inventoryReferenceType | string | No | Indicates the type of item indicated by the inventoryReferenceId . This value can be set to either INVENTORY_ITEM or INVENTORY_ITEM_GROUP . Required if if you supply an inventoryReferenceId . For implementation help, refer to eBay API documentation |
| reportTasks.listingIds | array<string> | No | If supplied in the request, this field returns a list of the listing IDs included in the report. A listing ID is an eBay-assigned ID that's generated when a listing is created. |
| reportTasks.marketplaceId | string | No | The ID of the eBay marketplace used by the report task. For implementation help, refer to eBay API documentation |
| reportTasks.metricKeys | array<string> | No | A list of metrics for the report task. |
| reportTasks.reportExpirationDate | string | No | The date after which the report is no longer be available. Reports are available for 30 days and you cannot download a report after it has expired. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ |
| reportTasks.reportFormat | string | No | Indicates the format of the report. Currently, only TSV_GZIP is supported. For implementation help, refer to eBay API documentation |
| reportTasks.reportHref | string | No | The URL of the generated report, which can be used to download the report once it has been generated. |
| reportTasks.reportId | string | No | A unique eBay-assigned ID for the report. |
| reportTasks.reportName | string | No | An eBay-assigned name for the report that's created by the createReportTask call. This name is unique for the seller. |
| reportTasks.reportTaskCompletionDate | string | No | The date the report task completed the report generation. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ |
| reportTasks.reportTaskCreationDate | string | No | The date the report task was created. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ |
| reportTasks.reportTaskExpectedCompletionDate | string | No | The date the report task is expected to complete the report generation. Format (UTC): yyyy-MM-ddThh:mm:ss.sssZ |
| reportTasks.reportTaskId | string | No | The unique eBay-assigned ID of the report task. This value is generated when the report task is created with a call to createReportTask . |
| reportTasks.reportTaskStatus | string | No | Indicates the current state of the report task. For implementation help, refer to eBay API documentation |
| reportTasks.reportTaskStatusMessage | string | No | A status message with additional information about the report task. |
| reportTasks.reportType | string | No | Indicates type of report associated with the report task. Note: INVENTORY_PERFORMANCE_REPORT is not currently available; availability date is pending. For implementation help, refer to eBay API documentation |
