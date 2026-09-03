---
title: Get_Payment_Dispute_Activity
category: Fulfillment_API
api_name: Get_Payment_Dispute_Activity
method: GET
path: /payment_dispute/{payment_dispute_id}/activity
---

**Category:** Fulfillment_API
**API:** Get_Payment_Dispute_Activity

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payment_dispute/{payment_dispute_id}/activity

## API Description
Get Payment Dispute Activity

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payment_dispute_id (path) | string | Yes | This parameter is used to specify the unique identifier of the payment dispute associated with the activity log being retrieved. Use the getPaymentDisputeSummaries method to retrieve payment dispute IDs. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| activity | array<PaymentDisputeActivity> | No | This array holds all activities of a payment dispute, from creation to resolution. For each activity, the activity type, the actor, and a timestamp is shown. The getActivities response is dynamic, and grows with each recorded activity. |
| activity.activityDate | string | No | The timestamp in this field shows the date/time of the payment dispute activity. The timestamps returned here use the ISO-8601 24-hour date and time format, and the time zone used is Universal Coordinated Time (UTC), also known as Greenwich Mean Time (GMT), or Zulu. The ISO-8601 format looks like th |
| activity.activityType | string | No | This enumeration value indicates the type of activity that occured on the payment dispute. For example, a value of DISPUTE_OPENED is returned when a payment disute is first created, a value indicating the seller's decision on the dispute, such as SELLER_CONTEST , is returned when seller makes a deci |
| activity.actor | string | No | This enumeration value indicates the actor that performed the action. Possible values include the BUYER , SELLER , CS_AGENT (eBay customer service), or SYSTEM . For implementation help, refer to eBay API documentation |
