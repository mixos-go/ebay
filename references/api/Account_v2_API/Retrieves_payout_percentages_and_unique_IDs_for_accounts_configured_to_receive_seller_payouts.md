---
title: Retrieves_payout_percentages_and_unique_IDs_for_accounts_configured_to_receive_seller_payouts
category: Account_v2_API
api_name: Retrieves_payout_percentages_and_unique_IDs_for_accounts_configured_to_receive_seller_payouts
method: GET
path: /payout_settings
---

**Category:** Account_v2_API
**API:** Retrieves_payout_percentages_and_unique_IDs_for_accounts_configured_to_receive_seller_payouts

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/payout_settings

## API Description
Retrieves payout percentages and unique IDs for accounts configured to receive seller payouts.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payoutInstruments | array<PayoutInstrument> | Yes | This array provides details about the seller's accounts defined for the seller's account. Payment accounts can only receive payouts if the status of the payout instrument is ACTIVE . |
| payoutInstruments.accountLastFourDigits | string | No | The last four digits of the account that the seller uses to receive payouts. This may be the last four digits of a bank account or a payment processor account such as Payoneer. |
| payoutInstruments.instrumentId | string | No | The unique reference identifier for a payout instrument. The instrumentId is needed to change the split-payout percentages through an updatePayoutPercentage request. |
| payoutInstruments.instrumentStatus | InstrumentStatusEnum | No | The status of a payout instrument. Valid payout instrument statuses include: PENDING: This status indicates that the account must be verified before it can be used. ACTIVE: This status indicates that payouts are enabled on this account. VERIFICATION_FAILED: This status indicates that verification ha |
| payoutInstruments.instrumentType | string | No | The type of account that received payouts. The value returned in this field may be: BANK : Indicates that the payout was made to a seller's bank account. CARD ( Not Currently Available ): Indicates that the payout went to a seller's debit card. The name of a digital wallet provider or payment proces |
| payoutInstruments.nickname | string | No | When instrumentType returns BANK , this value is the seller-provided nickname that the seller uses to represent the bank account that receives the payout. When instrumentType returns CARD , this value is the debit card network for the debit card that receives the payout. When instrumentType returns  |
| payoutInstruments.payoutPercentage | string | No | The current payout percentage allocated to an instrument. For example, 50 indicates that 50% of the payout goes to the instrument. |
