---
title: createReportTask
category: Marketing_API
api_name: createReportTask
method: POST
path: /ad_report_task
---

**Category:** Marketing_API
**API:** createReportTask

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/ad_report_task

## API Description
This method creates a report task , which generates a Promoted Listings report based on the values specified in the call. The report is generated based on the criteria you specify, including the report type, the report's dimensions and metrics, the report's start and end dates, the listings to include in the report, and more. Metrics are the quantitative measurements in the report while dimensions specify the attributes of the data included in the reports. When creating a report task, you can specify the items you want included in the report. The items you specify, using either listingId or inventoryReference values, must be in a Promoted Listings campaign for them to be included in the report. For details on the required and optional fields for each report type, see Promoted Listings reporting . This call returns the URL to the report task in the Location response header, and the URL includes the report-task ID. Reports often take time to generate and it's common for this call to return an HTTP status of 202 , which indicates the report is being generated. Call getReportTasks (or getReportTask with the report-task ID) to determine the status of a Promoted Listings report. When a report is complete, eBay sets its status to SUCCESS and you can download it using the URL returned in the reportHref field of the getReportTask call. Report files are tab-separated value gzip files with a file extension of .tsv.gz . Note: The reporting of some data related to sales and ad-fees may require a 72-hour ( maximum ) adjustment period which is often referred to as the Reconciliation Period . Such adjustment periods should, on average, be minimal. However, at any given time, the payments tab may be used to view those amounts that have actually been charged. Note: This call fails if you don't submit all the required fields for the specified report type. Fields not supported by the specified report type are ignored. Call getReportMetadata to retrieve a list of the fields you need to configure for each Promoted Listings report type. Important! For ad_report and ad_report_task methods, the API call limit is subject to a per user quota. These API calls can only be executed a maximum of 200 times per hour for each seller/user. If the number of calls per hour exceeds this limit, any new calls will be blocked for the next hour. Important! The data threshold for a single report is currently 1 million records; if this threshold is exceeded, the report will fail.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| additionalRecords | array<string> | No | A list of additional records that shall be included in the report, such as non-performing data. Note: Additional records are only applicable to Promoted Listings priority strategy campaigns that use the Cost Per Click (CPC) funding model. Valid Value: NON_PERFORMING_DATA |
| campaignIds | array<string> | No | A list of campaign IDs to be included in the report task. Use the getCampaigns method to retrieve a list of the current campaign IDs for a seller. For general campaign strategy sellers, this field is required if the reportType is set to CAMPAIGN_PERFORMANCE_REPORT or CAMPAIGN_PERFORMANCE_SUMMARY_REP |
| channels | array<string> | No | The channel for the advertising campaign that will be included in the report task. This value indicates whether the data included in the report task is for an Onsite or Offsite advertising campaign. If no value is entered, this field will default to ON_SITE . Multiple channels are not supported. Not |
| dateFrom | string | No | The date defining the start of the timespan covered by the report. Format the timestamp as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock with local offset. Note: The date specified cannot be a future date. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Exam |
| dateTo | string | No | The date defining the end of the timespan covered by the report. As with the dateFrom field, format the timestamp as an ISO 8601 string. Note: The date specified cannot be a future date. Additionally, the time specified must be a later time than that specified in the dateFrom field. Format: [YYYY]-[ |
| dimensions | array<Dimension> | No | The list of the dimensions applied to the report. A dimension is an attribute to which the report data applies. For example, if you set dimensionKey to campaign_id in a Campaign Performance Report, the data will apply to the entire ad campaign. For information on the dimensions and how to specify th |
| dimensions.annotationKeys | array<string> | No | A list of annotations associated with the dimension of the report. |
| dimensions.dimensionKey | string | No | The name of the dimension on which the report is based. A dimension is an attribute to which the report data applies. |
| fundingModels | array<string> | No | The funding model for the campaign that shall be included in the report. Note: The default funding model for Promoted Listings reports is COST_PER_SALE . Note: Multiple value support for the fundingModels array has been deprecated. See API&nbsp;Deprecation&nbsp;Status for information. Valid Values:  |
| inventoryReferences | array<InventoryReference> | No | You can use this field to supply an array of items to include in the report if you manage your inventory with the Inventory API . This field is mutually exclusive with the listingIds field; if you populate this field, do not populate the listingIds field. An inventory reference identifies an item in |
| inventoryReferences.inventoryReferenceId | string | No | The unique identifier of a single-item listing or a multi-variation listing. To create an ad for a single-item listing, set the inventoryReferenceType value to INVENTORY_ITEM and specify an item ID or a SKU (if the SKU is defined in the listing). To create an ad for a multi-variation listing, set th |
| inventoryReferences.inventoryReferenceType | string | No | Indicates the type of item indicated by the inventoryReferenceId . This value can be set to either INVENTORY_ITEM or INVENTORY_ITEM_GROUP . Required if if you supply an inventoryReferenceId . For implementation help, refer to eBay API documentation |
| listingIds | array<string> | No | Use this field to supply an array of eBay listing IDs you want to include in the report. Important: This field is mutually exclusive with the inventoryReferences field; if you populate this field, do not populate the inventoryReferences field. For general campaign strategy sellers, this field is req |
| marketplaceId | string | No | The unique identifier for the eBay marketplace on which the report is based. For implementation help, refer to eBay API documentation |
| metricKeys | array<string> | No | The list of metrics to be included in the report. Metrics are the quantitative measurements compiled into the report and the data returned is based on the specified dimension of the report. For example, if the dimension is campaign , the metrics for number of sales would be the number of sales in th |
| reportFormat | string | No | The file format of the report. Currently, the only supported format is TSV_GZIP , which is a gzip file with tab separated values. For implementation help, refer to eBay API documentation |
| reportType | string | No | The type of report to be generated, such as ACCOUNT_PERFORMANCE_REPORT or CAMPAIGN_PERFORMANCE_REPORT . Note: INVENTORY_PERFORMANCE_REPORT is not currently available; availability date is pending. Maximum: 1 For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
