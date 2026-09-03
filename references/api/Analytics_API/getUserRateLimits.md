---
title: getUserRateLimits
category: Analytics_API
api_name: getUserRateLimits
method: GET
path: /user_rate_limit/
---

**Category:** Analytics_API
**API:** getUserRateLimits

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/user_rate_limit/

## API Description
This method retrieves the call limit and utilization data for an application user. The call-limit data is returned for all RESTful APIs and the legacy Trading API that limit calls on a per-user basis. The response from getUserRateLimits includes a list of the applicable resources and the "call limit", or quota, that is set for each resource. In addition to quota information, the response also includes the number of remaining calls available before the limit is reached, the time remaining before the quota resets, the number of calls made to the specific resource, and the length of the "time window" to which the quota applies. By default, this method returns utilization data for all RESTful APIs resources and the legacy Trading API calls that limit request access by user. Use the api_name and api_context query parameters to filter the response to only the desired APIs. For more on call limits, see Application Growth Check .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| api_context (query) | string | No | This optional query parameter filters the result to include only the specified API context. Valid values: buy sell commerce developer tradingapi |
| api_name (query) | string | No | This optional query parameter filters the result to include only the APIs specified. Example values: browse for the Buy APIs inventory for the Sell APIs taxonomy for the Commerce APIs tradingapi for the Trading APIs |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rateLimits | array<RateLimit> | No | The rate-limit data for the specified APIs. The rate-limit data is returned for all the methods in the specified APIs and data pertains to the current time window. |
| rateLimits.apiContext | string | No | The context of the API for which rate-limit data is returned. For example buy , sell , commerce , developer or tradingapi . |
| rateLimits.apiName | string | No | The name of the API for which rate-limit data is returned. For example browse for the Buy API, inventory for the Sell API, taxonomy for the Commerce API, or tradingapi for Trading API. |
| rateLimits.apiVersion | string | No | The version of the API for which rate-limit data is returned. For example v1 or v2 . |
| rateLimits.resources | array<Resource> | No | A list of the methods for which rate-limit data is returned. For example item for the Feed API, getOrder for the Fulfillment API, getProduct for the Catalog API, AddItems for the Trading API. |
| rateLimits.resources.name | string | No | The name of the resource (an API or an API method) to which the rate-limit data applies. |
| rateLimits.resources.rates | array<Rate> | No | A list of rate-limit data, where each list element represents the rate-limit data for a specific resource. |
| rateLimits.resources.rates.count | integer | No | The number of calls a user has made to this resource within a set time period. This time period is defined by the associated timeWindow value. |
| rateLimits.resources.rates.limit | integer | No | The maximum number of requests that can be made to this resource during a set time period. The length of time to which the limit is applied is defined by the associated timeWindow value. This value is often referred to as the "call quota" for the resource. |
| rateLimits.resources.rates.remaining | integer | No | The remaining number of requests that can be made to this resource before the associated time window resets. |
| rateLimits.resources.rates.reset | string | No | The data and time the time window and accumulated calls for this resource reset. When the reset time is reached, the remaining value is reset to the value of limit , and this reset value is reset to the current time plus the number of seconds defined by the timeWindow value. The time stamp is format |
| rateLimits.resources.rates.timeWindow | integer | No | A period of time, expressed in seconds. The call quota for a resource is applied to the period of time defined by the value of this field. |
