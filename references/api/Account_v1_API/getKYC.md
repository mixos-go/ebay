---
title: getKYC
category: Account_v1_API
api_name: getKYC
method: GET
path: /kyc
---

**Category:** Account_v1_API
**API:** getKYC

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/kyc

## API Description
Note: This method was originally created to see which onboarding requirements were still pending for sellers being onboarded for eBay managed payments, but now that all seller accounts are onboarded globally, this method should now just return an empty payload with a 204 No Content HTTP status code.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| kycChecks | array<KycCheck> | No | This array contains one or more KYC checks required from a managed payments seller. The seller may need to provide more documentation and/or information about themselves, their company, or the bank account they are using for seller payouts. If no KYC checks are currently required from the seller, th |
| kycChecks.dataRequired | string | No | The enumeration value returned in this field categorizes the type of details needed for the KYC check. More information about the check is shown in the detailMessage and other applicable, corresponding fields. For implementation help, refer to eBay API documentation |
| kycChecks.dueDate | string | No | The timestamp in this field indicates the date by which the seller should resolve the KYC requirement. The timestamp in this field uses the UTC date and time format described in the ISO 8601 Standard . See below for this format and an example: MM-DD-YYYY HH:MM:SS 06-05-2020 10:34:18 |
| kycChecks.remedyUrl | string | No | If applicable and available, a URL will be returned in this field, and the link will take the seller to an eBay page where they can provide the requested information. |
| kycChecks.alert | string | No | This field gives a short summary of what is required from the seller. An example might be, ' Upload bank document now. '. The detailMessage field will often provide more details on what is required of the seller. |
| kycChecks.detailMessage | string | No | This field gives a detailed message about what is required from the seller. An example might be, ' Please upload a bank document by 2020-08-01 to get your account back in good standing. '. |
