---
title: getReportMetadataForReportType
category: Marketing_API
api_name: getReportMetadataForReportType
method: GET
path: /ad_report_metadata/{report_type}
---

**Category:** Marketing_API
**API:** getReportMetadataForReportType

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/ad_report_metadata/{report_type}

## API Description
This call retrieves metadata that details the fields used by a specific Promoted Listings report type. Use the report_type path parameter to indicate metadata to retrieve. This method does not use a request payload. Note: The reporting of some data related to sales and ad-fees may require a 72-hour ( maximum ) adjustment period which is often referred to as the Reconciliation Period . Such adjustment periods should, on average, be minimal. However, at any given time, the payments tab may be used to view those amounts that have actually been charged.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| report_type (path) | string | Yes | This path parameter specifies the name of the report type whose metadata you want to retrieve. For details about available report types and their descriptions, refer to the ReportTypeEnum . |
| funding_model (query) | string | No | The funding model used in the report. The funding model must be compatible with the report type specified in the path parameter. Refer to the FundingModelEnum type for supported values. |
| channel (query) | string | No | The channel used in the report. The channel must be compatible with the report type specified in the path parameter. Refer to the ChannelEnum type for supported values. Note: The channel parameter is only applicable for COST_PER_CLICK funding model. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| dimensionMetadata | array<DimensionMetadata> | No | A list containing the metadata for the dimension used in the report. |
| dimensionMetadata.dataType | string | No | The data type of the dimension value used to create the report. For implementation help, refer to eBay API documentation |
| dimensionMetadata.dimensionKey | string | No | The name of the dimension used to create the report. |
| dimensionMetadata.dimensionKeyAnnotations | array<DimensionKeyAnnotation> | No | An list of annotation keys associated with the specified dimension of the report. |
| dimensionMetadata.dimensionKeyAnnotations.annotationKey | string | No | An annotation key associated with the dimension. |
| dimensionMetadata.dimensionKeyAnnotations.dataType | string | No | The data type of the annotation key value. For implementation help, refer to eBay API documentation |
| maxNumberOfDimensionsToRequest | integer | No | The maximum number of dimensions that can be requested for the specified report type. |
| maxNumberOfMetricsToRequest | integer | No | The maximum number of metrics that can be requested for the specified report type. |
| channel | string | No | This field indicates whether a COST_PER_CLICK report type is related to an ON_SITE or OFF_SITE Promoted Listings campaign. This field is not returned for COST_PER_SALE report types since COST_PER_SALE campaigns are only available ON_SITE. For implementation help, refer to eBay API documentation |
| metricMetadata | array<MetricMetadata> | No | A list containing the metadata for the metrics in the report. |
| metricMetadata.dataType | string | No | The data type of the returned metric value. For implementation help, refer to eBay API documentation |
| metricMetadata.metricKey | string | No | The name of the metric. |
| reportType | string | No | The report_type , as specified in the request to create the report task. Note: INVENTORY_PERFORMANCE_REPORT is not currently available; availability date is pending. For implementation help, refer to eBay API documentation |
