---
title: getPrivileges
category: Account_v1_API
api_name: getPrivileges
method: GET
path: /privilege
---

**Category:** Account_v1_API
**API:** getPrivileges

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/privilege

## API Description
This method retrieves the seller's current set of privileges, including whether or not the seller's eBay registration has been completed, as well as the details of their site-wide sellingLimit (the amount and quantity they can sell on a given day).

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sellerRegistrationCompleted | boolean | No | If this field is returned as true , the seller's registration is completed. If this field is returned as false , the registration process is not complete. |
| sellingLimit | SellingLimit | No | This container lists the monthly cap for the quantity of items sold and total sales amount allowed for the seller's account. This container may not be returned if a seller does not have a monthly cap for total quantity sold and total sales amount. Note: The selling limit value returned in getPrivile |
| sellingLimit.amount | Amount | No | This container shows the monthly cap for total sales amount allowed for the seller's account. This container may not be returned if a seller does not have a monthly cap for total sales amount. |
| sellingLimit.amount.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD . Default: The default currency of the eBay marketplace that hosts the listing. For implementation help, |
| sellingLimit.amount.value | string | No | The monetary amount in the specified currency . |
| sellingLimit.quantity | integer | No | This field shows the monthly cap for total quantity sold allowed for the seller's account. This field may not be returned if a seller does not have a monthly cap for total quantity sold. |
