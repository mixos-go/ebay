---
title: Updates_the_split-payout_percentage_for_two_payout_instruments_for_sellers_in_mainland_China
category: Account_v2_API
api_name: Updates_the_split-payout_percentage_for_two_payout_instruments_for_sellers_in_mainland_China
method: POST
path: /payout_settings/update_percentage
---

**Category:** Account_v2_API
**API:** Updates_the_split-payout_percentage_for_two_payout_instruments_for_sellers_in_mainland_China

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/payout_settings/update_percentage

## API Description
Updates the split-payout percentage for two payout instruments for sellers in mainland China.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payoutInstruments | array<UpdatePayoutPercentage> | Yes | This array allows the seller to set the payout split percentages for two accounts enabled to receive payouts. |
| payoutInstruments.instrumentId | string | No | The unique reference identifier for a payout instrument. This value is returned in the getPayoutSettings response and is needed to change split-payout percentages through an updatePayoutPercentage request. |
| payoutInstruments.payoutPercentage | string | No | The user-defined payout percentage allocated to this instrument. For example, 50 indicates that 50% of the payout goes to this instrument. The split-payout percentage must be a positive integer value from 0-100. The values of two instruments must always add up to 100%. If the values do not equal 100 |

## Response
_No documented response fields._
