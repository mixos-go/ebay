---
title: getPaymentsProgramOnboarding
category: Account_v1_API
api_name: getPaymentsProgramOnboarding
method: GET
path: /payments_program/{marketplace_id}/{payments_program_type}/onboarding
---

**Category:** Account_v1_API
**API:** getPaymentsProgramOnboarding

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payments_program/{marketplace_id}/{payments_program_type}/onboarding

## API Description
Note: This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow. This method retrieves a seller's onboarding status for a payments program for a specified marketplace. The overall onboarding status of the seller and the status of each onboarding step is returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (path) | string | Yes | The eBay marketplace ID associated with the onboarding status to retrieve. |
| payments_program_type (path) | string | Yes | The type of payments program whose status is returned by the method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| onboardingStatus | string | No | This enumeration value indicates the eligibility of payment onboarding for the registered site. For implementation help, refer to eBay API documentation |
| steps | array<PaymentsProgramOnboardingSteps> | No | An array of the active process steps for payment onboarding and the status of each step. This array includes the step name , step status , and a webUrl to the IN_PROGRESS step. The step names are returned in sequential order. |
| steps.name | string | No | The name of the step in the steps array. Over time, these names are subject to change as processes change. The output sample contains example step names. Review an actual call response for updated step names. |
| steps.status | string | No | This enumeration value indicates the status of the associated step. Note: Only one step can be IN_PROGRESS at a time. For implementation help, refer to eBay API documentation |
| steps.webUrl | string | No | This URL provides access to the IN_PROGRESS step. |
