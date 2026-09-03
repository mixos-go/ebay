---
title: getDestinations
category: Notification_API
api_name: getDestinations
method: GET
path: /destination
---

**Category:** Notification_API
**API:** getDestinations

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/destination

## API Description
This method allows applications to retrieve a paginated collection of destination resources and related details. The details include the destination names, statuses, and configurations, including the endpoints and verification tokens.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| continuation_token (query) | string | No | This string value can be used to return the next page in the result set. The string to use here is returned in the next field of the current page of results. |
| limit (query) | string | No | The maximum number of destinations to return per page from the result set. Min: 10 Max: 100 Default: 20 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| destinations | array<Destination> | No | An array that contains the destination details. |
| destinations.deliveryConfig | DeliveryConfig | No | The configuration associated with this destination. |
| destinations.deliveryConfig.endpoint | string | No | The endpoint for this destination. Note: The provided endpoint URL should use the HTTPS protocol, and it should not contain an internal IP address or localhost in its path. |
| destinations.deliveryConfig.verificationToken | string | No | The verification token associated with this endpoint. Note: The provided verification token must be between 32 and 80 characters. Allowed characters include alphanumeric characters, underscores ( _ ), and hyphens ( - ); no other characters are allowed. |
| destinations.destinationId | string | No | The unique identifier for the destination. |
| destinations.name | string | No | The name associated with this destination. |
| destinations.status | string | No | The status for this destination. Note: The MARKED_DOWN value is set by eBay systems and cannot be used in a create or update call by applications. Valid values: ENABLED DISABLED MARKED_DOWN For implementation help, refer to eBay API documentation |
| href | string | No | The path to the call URI that produced the current page of results. |
| limit | integer | No | The number of records to show in the current response. Default: 20 |
| next | string | No | The URL to access the next set of results. This field includes a continuation_token . No prev field is returned, but this value is persistent during the session so that you can use it to return to the next page. This field is not returned if fewer records than specified by the limit field are return |
| total | integer | No | The total number of matches for the search criteria. |
