---
title: getSubscription
category: Account_v1_API
api_name: getSubscription
method: GET
path: /subscription
---

**Category:** Account_v1_API
**API:** getSubscription

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/subscription

## API Description
This method retrieves a list of subscriptions associated with the seller account.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | This field is for future use. |
| continuation_token (query) | string | No | This field is for future use. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | This field is for future use. |
| limit | integer | No | This field is for future use. |
| next | string | No | This field is for future use. |
| subscriptions | array<Subscription> | No | An array of subscriptions associated with the seller account. |
| subscriptions.marketplaceId | string | No | The marketplace with which the subscription is associated. For implementation help, refer to eBay API documentation |
| subscriptions.subscriptionId | string | No | The subscription ID. |
| subscriptions.subscriptionLevel | string | No | The subscription level. For example, subscription levels for an eBay store include Starter, Basic, Featured, Anchor, and Enterprise levels. |
| subscriptions.subscriptionType | string | No | The kind of entity with which the subscription is associated, such as an eBay store. For implementation help, refer to eBay API documentation |
| subscriptions.term | TimeDuration | No | The term of the subscription plan (typically in months). |
| subscriptions.term.unit | string | No | These enum values represent the time measurement unit, such as DAY . A span of time is defined when you apply the value specified in the value field to the value specified for unit . See TimeDurationUnitEnum for a complete list of possible time-measurement units. For implementation help, refer to eB |
| subscriptions.term.value | integer | No | An integer that represents an amount of time, as measured by the time-measurement unit specified in the unit field. |
| total | integer | No | The total number of subscriptions displayed on the current page of results. |
