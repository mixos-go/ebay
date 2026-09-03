---
title: getReportMetadata
category: Marketing_API
api_name: getReportMetadata
method: GET
path: /ad_report_metadata
---

**Category:** Marketing_API
**API:** getReportMetadata

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_report_metadata

## API Description
This call retrieves information that details the fields used in each of the Promoted Listings reports. Use the returned information to configure the different types of Promoted Listings reports. You can retrieve metadata for all report types,funding models and channels, or you can filter based on funding model and/or channel. Note: The reporting of some data related to sales and ad-fees may require a 72-hour ( maximum ) adjustment period which is often referred to as the Reconciliation Period . Such adjustment periods should, on average, be minimal. However, at any given time, the payments tab may be used to view those amounts that have actually been charged.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| funding_model (query) | string | No | This query parameter is used only if the user wants to see report metadata for a specific funding model. Refer to the FundingModelEnum type for supported values. |
| channel (query) | string | No | This query parameter is used only if the user wants to see COST_PER_CLICK report metadata for a specific channel. Refer to the ChannelEnum type for supported values. Note: The channel parameter is only applicable for COST_PER_CLICK funding model. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| reportMetadata | array<ReportMetadata> | No | A list of the metadata for the associated report type. |
| reportMetadata.dimensionMetadata | array<DimensionMetadata> | No | A list containing the metadata for the dimension used in the report. |
| reportMetadata.dimensionMetadata.dataType | string | No | The data type of the dimension value used to create the report. For implementation help, refer to eBay API documentation |
| reportMetadata.dimensionMetadata.dimensionKey | string | No | The name of the dimension used to create the report. |
| reportMetadata.dimensionMetadata.dimensionKeyAnnotations | array<DimensionKeyAnnotation> | No | An list of annotation keys associated with the specified dimension of the report. |
| reportMetadata.dimensionMetadata.dimensionKeyAnnotations.annotationKey | string | No | An annotation key associated with the dimension. |
| reportMetadata.dimensionMetadata.dimensionKeyAnnotations.dataType | string | No | The data type of the annotation key value. For implementation help, refer to eBay API documentation |
| reportMetadata.maxNumberOfDimensionsToRequest | integer | No | The maximum number of dimensions that can be requested for the specified report type. |
| reportMetadata.maxNumberOfMetricsToRequest | integer | No | The maximum number of metrics that can be requested for the specified report type. |
| reportMetadata.channel | string | No | This field indicates whether a COST_PER_CLICK report type is related to an ON_SITE or OFF_SITE Promoted Listings campaign. This field is not returned for COST_PER_SALE report types since COST_PER_SALE campaigns are only available ON_SITE. For implementation help, refer to eBay API documentation |
| reportMetadata.metricMetadata | array<MetricMetadata> | No | A list containing the metadata for the metrics in the report. |
| reportMetadata.metricMetadata.dataType | string | No | The data type of the returned metric value. For implementation help, refer to eBay API documentation |
| reportMetadata.metricMetadata.metricKey | string | No | The name of the metric. |
| reportMetadata.reportType | string | No | The report_type , as specified in the request to create the report task. Note: INVENTORY_PERFORMANCE_REPORT is not currently available; availability date is pending. For implementation help, refer to eBay API documentation |
