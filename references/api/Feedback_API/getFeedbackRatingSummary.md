---
title: getFeedbackRatingSummary
category: Feedback_API
api_name: getFeedbackRatingSummary
method: GET
path: /feedback_rating_summary
---

**Category:** Feedback_API
**API:** getFeedbackRatingSummary

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/feedback_rating_summary

## API Description
This method provides a detailed overview of feedback ratings associated with a user in the eBay marketplace. Specify a user ID and apply filters to retrieve summarized feedback data categorized by rating types and user roles. These returned metrics are aggregated, which offers insight into user experiences and performance. Tip: You can use this method to help sellers and buyers understand their marketplace reputation and identify areas for improvement. Returned data provides a summary of feedback ratings for a user by rating type (such as overall experience, communication, or delivery timeliness) for both buyer and seller roles. Each type of rating includes aggregated metrics like averages, counts, unique feedback givers, and the percentage of positive ratings (excluding neutrals). The response also details the distribution of specific rating values, their frequency, and time period (with period units like days or months) over which these metrics were calculated.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | Yes | Use this parameter to limit the response based on specified filter values: ratingType : Specifies the type of rating being summarized and returned (Required) . Available values: OVERALL_EXPERIENCE , OVERALL_EXPERIENCE_COMMENT , ON_TIME_DELIVERY , DSR_ITEM_AS_DESCRIBED , DSR_COMMUNICATION , DSR_SHIPP |
| user_id (query) | string | Yes | Use this parameter to specify the unique identifier (the eBay username associated with the account) for the eBay user whose feedback summary is being retrieved. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedbackRatingSummary | array<FeedbackRatingSummary> | No | An array containing a summary of feedback ratings. Each element provides detailed metrics and distributions for specific rating types. |
| feedbackRatingSummary.ratingSummaryByRatingType | array<RatingSummaryByRatingType> | No | An array that includes metrics and distributions for each rating type. |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackMetrics | array<FeedbackMetrics> | No | An array of metrics associated with feedback aggregation. |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackMetrics.metricName | string | No | This enumerated value specifies the type of feedback aggregation. For example, AVG would indicate the feedback returned represents the average value of the feedback. See metricValue for the value of the returned feedback. For implementation help, refer to eBay API documentation |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackMetrics.metricValue | number | No | The decimal value of the specified metric. For example, 55.8 would represent a value associated with the metricName (see metricName for interpretation and units). |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackRatingValueDistribution | array<FeedbackRatingValueDistribution> | No | An array listing the distribution values of the feedback ratings. |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackRatingValueDistribution.count | integer | No | An integer representing the number of occurrences for a specific feedback rating value . For example, for the POSITIVE value , a 3 returned as the count represents three positive ratings were returned. |
| feedbackRatingSummary.ratingSummaryByRatingType.feedbackRatingValueDistribution.value | string | No | A string indicating the specific feedback rating value. Supported values include: POSITIVE , NEUTRAL , NEGATIVE , 1 , 2 , 3 , 4 , and 5 . |
| feedbackRatingSummary.ratingSummaryByRatingType.period | Period | No | The time period on which the feedback summary is calculated. |
| feedbackRatingSummary.ratingSummaryByRatingType.period.unit | string | No | The unit of the period's value . Supported value: DAY . |
| feedbackRatingSummary.ratingSummaryByRatingType.period.value | integer | No | The value for the feedback period, specified in units of unit . Supported value: 90 . |
| feedbackRatingSummary.ratingSummaryByRatingType.userRoleType | string | No | This enumerated value indicates the user's role in the feedback ( BUYER or SELLER ). For implementation help, refer to eBay API documentation |
| feedbackRatingSummary.ratingType | string | No | This enumerated value indicates the type of rating being summarized. For example, OVERALL_EXPERIENCE indicates the rating applies to the overall transaction experience. For implementation help, refer to eBay API documentation |
