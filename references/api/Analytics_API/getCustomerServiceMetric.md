---
title: getCustomerServiceMetric
category: Analytics_API
api_name: getCustomerServiceMetric
method: GET
path: /customer_service_metric/{customer_service_metric_type}/{evaluation_type}
---

**Category:** Analytics_API
**API:** getCustomerServiceMetric

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/customer_service_metric/{customer_service_metric_type}/{evaluation_type}

## API Description
Use this method to retrieve a seller's performance and rating for the customer service metric. Control the response from the getCustomerServiceMetric method using the following path and query parameters: customer_service_metric_type controls the type of customer service transactions evaluated for the metric rating. evaluation_type controls the period you want to review. evaluation_marketplace_id specifies the target marketplace for the evaluation. Currently, metric data is returned for only peer benchmarking. For details on the workings of peer benchmarking, see Service metrics policy . For details on using and understanding the response from this method, see Interpreting customer service metric ratings .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| customer_service_metric_type (path) | string | Yes | Use this path parameter to specify the type of customer service metrics and benchmark data you want returned for the seller. Supported types are: ITEM_NOT_AS_DESCRIBED ITEM_NOT_RECEIVED |
| evaluation_marketplace_id (query) | string | Yes | Use this query parameter to specify the Marketplace ID to evaluate for the customer service metrics and benchmark data. For the list of supported marketplaces, see Analytics API requirements and restrictions . For implementation help, refer to eBay API documentation at https://developer.ebay.com/api |
| evaluation_type (path) | string | Yes | Use this path parameter to specify the evaluation period to use for the performance metrics. See EvaluationTypeEnum for more information on the supported values. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| dimensionMetrics | array<DimensionMetric> | No | This container provides a seller's customer service metric performance for a given dimension . In the getCustomerServiceMetric request, specify values for the following request parameters to control the returned dimension and the associated metric values: customer_service_metric_type evaluation_type |
| dimensionMetrics.dimension | Dimension | No | This type defines the "dimension," or attributes, against which the associated customer service metric values and benchmark ratings are based. The dimensionKey value is set according to the customer_service_metric_type request parameter and the values in the associated name / value pairs relate to t |
| dimensionMetrics.dimension.dimensionKey | string | No | dimensionKey defines the basis against which the seller's customer service metric is measured. The value of this field gets set according to the value of the customer_service_metric_type input parameter. The following input configurations return the responses shown: ITEM_NOT_AS_DESCRIBED &ndash; Ret |
| dimensionMetrics.dimension.name | string | No | The dimension name returned in this field depends on the dimensionKey : If dimensionKey is set to SHIPPING_REGION , this field is set to one of following values, which represent established shipping corridors: Domestic International: Mature region International: Emerging region If dimensionKey is se |
| dimensionMetrics.dimension.value | string | No | The value returned in this field depends on the dimensionKey . If dimensionKey equals LISTING_CATEGORY , the value returned in this field is the category ID of the primary (L1) category in which the items being rated were listed. If dimensionKey equals SHIPPING_REGION , one of the following values i |
| dimensionMetrics.metrics | array<Metric> | No | This is a list of Metric elements where each element contains data and information related to the transactions grouped by the associated dimension . |
| dimensionMetrics.metrics.benchmark | MetricBenchmark | No | This complex type defines a set of benchmark data, which includes the average rating for the group included in the benchmark evaluation and the seller's calculated customer service metric rating for the benchmark. This container is returned only if the associated metricKey value is RATE . |
| dimensionMetrics.metrics.benchmark.adjustment | string | No | If this field is present, it indicates that the rating given to the seller was "adjusted" for one reason or another. If eBay determines that the normal rating of a seller is impacted by circumstances beyond their control, they can issue an override to adjust the rating given to the seller. For imple |
| dimensionMetrics.metrics.benchmark.basis | string | No | This field returns the "basis" by which the benchmark is calculated for the customer service metric type. Currently, the only supported basis is PEER_BENCHMARK . For implementation help, refer to eBay API documentation |
| dimensionMetrics.metrics.benchmark.metadata | BenchmarkMetadata | No | This field contains the benchmark data. |
| dimensionMetrics.metrics.benchmark.metadata.average | string | No | This field returns the average value for the group, as defined by the specified basis . When the benchmark basis is set to PEER_BENCHMARK , the value returned in this field is the benchmark value to which the seller's metric value is compared to determine the seller's rating for the customer service |
| dimensionMetrics.metrics.benchmark.rating | string | No | This field returns seller's rating for the customer service metric. The rating is set to a value that equals the relative deviation between the seller's metric value and the benchmark value for the customer service metric. Deviation values range from LOW to VERY HIGH , and the lower the deviation, t |
| dimensionMetrics.metrics.distributions | array<MetricDistribution> | No | Returned when metricKey equals COUNT , this field returns an array of seller data where each set of data is grouped according by an overarching basis . When the seller distribution is returned, the numeric value of the associated value container equals the sum of the transactions where the seller me |
| dimensionMetrics.metrics.distributions.basis | string | No | This field returns the basis, or the method, by which the metric rating is calculated. |
| dimensionMetrics.metrics.distributions.data | array<Distribution> | No | This field returns a list of name/value pairs, where the name indicates the distribution being rated and the value indicates the count of seller transactions that meet the distribution criteria. |
| dimensionMetrics.metrics.distributions.data.name | string | No | The name of a distribution in which the seller is active. |
| dimensionMetrics.metrics.distributions.data.value | string | No | This field contains the number of transactions the seller had in the distribution (identified by the associated name field) during the metric evaluationCycle . |
| dimensionMetrics.metrics.metricKey | string | No | This field indicates the customer service metric being returned in the associated metrics container. The field is set as follows: TRANSACTION_COUNT &ndash; When set to this value, the associated value field returns the number of transactions completed in the peer group for the metric being evaluated |
| dimensionMetrics.metrics.value | string | No | This field is set to the seller's numeric rating for the associated metricKey for the given dimension during the evaluationCycle . To determine the seller's rating for this metric, the value of this field is compared to the average metric value of the group. |
| evaluationCycle | EvaluationCycle | No | This complex type defines the evaluation type ( CURRENT or PROJECTED ) and the transaction lookback period used to calculate the seller's customer service metric. |
| evaluationCycle.endDate | string | No | End date and time of the transaction lookback range. All timestamps are based on Mountain Standard Time (MST). The timestamp is formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. |
| evaluationCycle.evaluationDate | string | No | The ISO-8601 date and time at which the seller was evaluated for this customer service metric rating. |
| evaluationCycle.evaluationType | string | No | This field specifies the transaction lookback period used for the evaluation. The evaluation_type value specified in the request is returned in this field. There are two possible values: CURRENT &ndash; A monthly evaluation that occurs on the 20th of every month. PROJECTED &ndash; A daily evaluation |
| evaluationCycle.startDate | string | No | The start date and time of the transaction lookback range. All timestamps are based on Mountain Standard Time (MST). The timestamp is formatted as an ISO 8601 string, which is based on the 24-hour Coordinated Universal Time (UTC) clock. Format: [YYYY]-[MM]-[DD]T[hh]:[mm]:[ss].[sss]Z Example: 2018-08 |
| marketplaceId | string | No | The eBay marketplace ID of the marketplace upon which the customer service metric evaluation is based. The customer_service_metric resource supports a limited set of marketplaces. For a complete list of the supported marketplaces, please see the Service metrics policy page. For implementation help,  |
