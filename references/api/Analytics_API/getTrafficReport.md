---
title: getTrafficReport
category: Analytics_API
api_name: getTrafficReport
method: GET
path: /traffic_report
---

**Category:** Analytics_API
**API:** getTrafficReport

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/traffic_report

## API Description
This method returns a report that details the user traffic received by a seller's listings. A traffic report gives sellers the ability to review how often their listings appeared on eBay, how many times their listings are viewed, and how many purchases were made. The report also returns the report's start and end dates, and the date the information was last updated. For more information, see Traffic report details

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| dimension (query) | string | No | This query parameter specifies the dimension , or "attribute," that is applied to the report metric . Valid values: DAY or LISTING Examples If you specify dimension=DAY and metric=CLICK_THROUGH_RATE , the traffic report contains the number of times an item displayed on a search results page and the  |
| filter (query) | string | No | This query parameter refines the information returned in the traffic report. Note: URL encode all the values you supply in the filter parameter. See URL encoding query parameter values as described in URL parameters . Configure the following properties of the filter parameter to tune the traffic rep |
| metric (query) | string | No | This query parameter specifies the metrics you want covered in the report. Note: Unlike names for parameters and enumerated values, metric values are not case sensitive. Valid values: CLICK_THROUGH_RATE LISTING_IMPRESSION_SEARCH_RESULTS_PAGE LISTING_IMPRESSION_STORE LISTING_IMPRESSION_TOTAL LISTING_ |
| sort (query) | string | No | This query parameter sorts the report on the specified metric. You can only specify a single metric in the sort parameter and the specified metric must be included in the configuration of the report's metric parameter. Sorting is helpful when you want to review how a specific metric is performing, s |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| dimensionMetadata | array<Metadata> | No | A complex type containing the header of the report and the type of data containted in the rows of the report. |
| dimensionMetadata.metadataHeader | MetadataHeader | No | The container that returns the dimensionKeys and metrics headers for the report. |
| dimensionMetadata.metadataHeader.key | string | No | The key value used for the report. For example: "key": "LISTING_ID" |
| dimensionMetadata.metadataHeader.metadataKeys | array<Definition> | No | The list of dimension key values used for the report header. Each list element contains the key name, its data type, and its localized name. For example: "metadataKeys": [ &nbsp;&nbsp;"key": "LISTING_TITLE", &nbsp;&nbsp;"localizedName": "Listing title", &nbsp;&nbsp;"dataType": "STRING" |
| dimensionMetadata.metadataHeader.metadataKeys.dataType | string | No | Indicates the data type of the returned dimension. For example, if the dimension is day , the data type is DATE . For implementation help, refer to eBay API documentation |
| dimensionMetadata.metadataHeader.metadataKeys.key | string | No | The value the dimension or metric parameter as submitted in the request. |
| dimensionMetadata.metadataHeader.metadataKeys.localizedName | string | No | The localized name of the metric or dimension (translated into the language specified in the Accept-Language HTTP request header). For example, if Accept-Language is set to de-DE , the value "day" in the dimension container is returned as "tag", and a metric of TRANSACTION is returned as "Transaktio |
| dimensionMetadata.metadataRecords | array<MetadataRecord> | No | A list of the individual report records. |
| dimensionMetadata.metadataRecords.metadataValues | array<Value> | No | A list of data in a row returned in the traffic report. The data in each of the cells match the labels in headers of the report. |
| dimensionMetadata.metadataRecords.metadataValues.applicable | boolean | No | If set to true , this flag indicates the value in the value field is valid as computed. A value of false indicates one or more of the values used to calculate the value was invalid. The occurrence of this is a rare, however consider this case: suppose a buyer navigates to a View Item page at 11:59 p |
| dimensionMetadata.metadataRecords.metadataValues.value | object | No | The value of the report data. |
| dimensionMetadata.metadataRecords.value | Value | No | The value of the key on which the report is based. For example, if the key is the listing ID, the value of this container could be: "value": { &nbsp;&nbsp;"value": "142133954229", &nbsp;&nbsp;"applicable": true } |
| dimensionMetadata.metadataRecords.value.applicable | boolean | No | If set to true , this flag indicates the value in the value field is valid as computed. A value of false indicates one or more of the values used to calculate the value was invalid. The occurrence of this is a rare, however consider this case: suppose a buyer navigates to a View Item page at 11:59 p |
| dimensionMetadata.metadataRecords.value.value | object | No | The value of the report data. |
| endDate | string | No | The time stamp is formatted as an ISO 8601 string, which is based on the 24-hour Universal Coordinated Time (UTC) clock. If you specify an end date that is beyond the lastUpdatedDate value, eBay returns a report that contains data only up to the lastUpdateDate date. Format: [YYYY]-[MM]-[DD]T[hh]:[mm |
| header | Header | No | A complex type containing the header for the report. |
| header.dimensionKeys | array<Definition> | No | A list of the dimension or metric keys returned in the report. The values for each are is returned in the associated key fields. |
| header.dimensionKeys.dataType | string | No | Indicates the data type of the returned dimension. For example, if the dimension is day , the data type is DATE . For implementation help, refer to eBay API documentation |
| header.dimensionKeys.key | string | No | The value the dimension or metric parameter as submitted in the request. |
| header.dimensionKeys.localizedName | string | No | The localized name of the metric or dimension (translated into the language specified in the Accept-Language HTTP request header). For example, if Accept-Language is set to de-DE , the value "day" in the dimension container is returned as "tag", and a metric of TRANSACTION is returned as "Transaktio |
| header.metrics | array<Definition> | No | The list of metrics returned in the report. The values for each are is returned in the associated key fields. |
| header.metrics.dataType | string | No | Indicates the data type of the returned dimension. For example, if the dimension is day , the data type is DATE . For implementation help, refer to eBay API documentation |
| header.metrics.key | string | No | The value the dimension or metric parameter as submitted in the request. |
| header.metrics.localizedName | string | No | The localized name of the metric or dimension (translated into the language specified in the Accept-Language HTTP request header). For example, if Accept-Language is set to de-DE , the value "day" in the dimension container is returned as "tag", and a metric of TRANSACTION is returned as "Transaktio |
| lastUpdatedDate | string | No | The date and time, in ISO 8601 format, that indicates the last time the data returned in the report was updated. |
| records | array<Record> | No | A complex type containing the individual data records for the traffic report. |
| records.dimensionValues | array<Value> | No | A list where each element contains either the string DAY (if the dimension is DAY ), or the listing ID for which the record's metric data is computed. A second array member, applicable , is always true for dimension values. |
| records.dimensionValues.applicable | boolean | No | If set to true , this flag indicates the value in the value field is valid as computed. A value of false indicates one or more of the values used to calculate the value was invalid. The occurrence of this is a rare, however consider this case: suppose a buyer navigates to a View Item page at 11:59 p |
| records.dimensionValues.value | object | No | The value of the report data. |
| records.metricValues | array<Value> | No | A list where each element contains a value field that indicates the record's value for the metric. Each element also contains an applicable field that indicates the veracity of the computed value . Note that there are no metric names or IDs associated with the values returned in this array. The meta |
| records.metricValues.applicable | boolean | No | If set to true , this flag indicates the value in the value field is valid as computed. A value of false indicates one or more of the values used to calculate the value was invalid. The occurrence of this is a rare, however consider this case: suppose a buyer navigates to a View Item page at 11:59 p |
| records.metricValues.value | object | No | The value of the report data. |
| startDate | string | No | The start date of the date range used to calculate the report, in ISO 8601 format. |
| warnings | array<Error> | No | An array of any process errors or warnings that were generated during the processing of the call processing. |
| warnings.category | string | No | Identifies whether the error was in the REQUEST or happened when running the APPLICATION. |
| warnings.domain | string | No | The primary system where the error occurred. This is relevant for application errors. For Analytics errors, it always has the value API_ANALYTICS . |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. Traffic report error IDs range from 50001 to 50500. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | A more detailed explanation of the error than given in the message error field. |
| warnings.message | string | No | Information on how to correct the problem, in the end user's terms and language where applicable. Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional list of name/value pairs that contain context-specific ErrorParameter objects, with each item in the list being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the entity that threw the error. |
| warnings.parameters.value | string | No | A description of the error. |
| warnings.subdomain | string | No | If present, indicates which subsystem in which the error occurred. |
