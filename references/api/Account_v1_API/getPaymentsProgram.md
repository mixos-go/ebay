---
title: getPaymentsProgram
category: Account_v1_API
api_name: getPaymentsProgram
method: GET
path: /payments_program/{marketplace_id}/{payments_program_type}
---

**Category:** Account_v1_API
**API:** getPaymentsProgram

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payments_program/{marketplace_id}/{payments_program_type}

## API Description
Note: This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow. This method returns whether or not the user is opted-in to the specified payments program. Sellers opt-in to payments programs by marketplace and you use the marketplace_id path parameter to specify the marketplace of the status flag you want returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace of the payments program for which you want to retrieve the seller's status. |
| payments_program_type (path) | string | Yes | This path parameter specifies the payments program whose status is returned by the call. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplaceId | string | No | The ID of the eBay marketplace to which the payment program applies. For implementation help, refer to eBay API documentation |
| paymentsProgramType | string | No | This parameter specifies the payment program whose status is returned by the call. Currently the only supported payments program is EBAY_PAYMENTS . For implementation help, refer to eBay API documentation |
| status | string | No | The enumeration value returned in this field indicates whether or not the seller's account is enabled for the payments program. For implementation help, refer to eBay API documentation |
| wasPreviouslyOptedIn | boolean | No | If returned as true , the seller was at one point opted-in to the associated payment program, but they later opted out of the program. A value of false indicates the seller never opted-in to the program or if they did opt-in to the program, they never opted-out of it. It's important to note that the |
