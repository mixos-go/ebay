---
title: Modifies_one_or_more_preferences_for_a_seller_on_a_specific_marketplace
category: Account_v2_API
api_name: Modifies_one_or_more_preferences_for_a_seller_on_a_specific_marketplace
method: PATCH
path: /user_preferences
---

**Category:** Account_v2_API
**API:** Modifies_one_or_more_preferences_for_a_seller_on_a_specific_marketplace

**Method:** PATCH
**HTTP Path:** https://api.ebay.com{basePath}/user_preferences

## API Description
Modifies one or more preferences for a seller on a specific marketplace.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedPaymentPreferences | CombinedPaymentPreferencesType | No | This container is included if the seller wishes to allow combined invoices if the buyer has multiple unpaid orders from the same seller. |
| combinedPaymentPreferences.combinedPaymentOption | CombinedPaymentOptionEnum | No | This enum type defines the available options for handling combined payments when a seller allows multiple line items from the same buyer to be paid for with a single payment. See CombinedPaymentOptionEnum for a description of each value. |
| dispatchCutoffTimePreference | DispatchCutoffTimePreferencesType | No | This container is included if the seller wishes to set or modify the order cut-off time for same-day shipping. |
| dispatchCutoffTimePreference.cutoffTime | string | No | This field indicates the dispatch cut-off time in Zulu format ( HH:mm:ss.SSSZ ) - 24-hour format with milliseconds and Z timezone indicator. Note: Despite the Z that is returned in the timestamp, the cut-off time is actually based on the default timezone of the eBay marketplace for the seller. Note: |
| emailShipmentTrackingNumberPreference | boolean | No | This field is included if the seller wishes to enable or disable the setting that will automatically email the buyer with the tracking number when it becomes available. |
| endOfAuctionEmailPreferences | EndOfAuctionEmailPreferencesType | No | This container is included if the seller wishes to change one or more of the end of auction email preferences. |
| endOfAuctionEmailPreferences.emailCustomized | boolean | No | This boolean field indicates whether or not the seller is using a customized email to send to winning bidders. |
| endOfAuctionEmailPreferences.logoCustomized | boolean | No | This boolean field indicates whether or not the seller is using a customized logo in the emails that are sent to winning bidders. |
| endOfAuctionEmailPreferences.logoType | EndOfAuctionLogoTypeEnum | No | This enum indicates the type of logo that is used in the email that is sent to winning bidders. See EndOfAuctionLogoTypeEnum type for descriptions of the different logo types. |
| endOfAuctionEmailPreferences.logoUrl | string | No | This field shows the URL path to a seller’s custom logo image that is being used in the email sent to winning bidders. This field is only returned if the seller is using a customized logo in emails. |
| endOfAuctionEmailPreferences.templateText | string | No | This field shows the body text that is being used if the seller is sending customized emails to winning bidders. The template text has a maximum limit of 1000 characters. |
| endOfAuctionEmailPreferences.textCustomized | boolean | No | This boolean field indicates whether or not the seller is using customized text in the emails that are sent to winning bidders. |
| globalShippingProgramListingPreference | boolean | No | This boolean field is included if the seller wishes to toggle the setting that controls whether or not the seller’s new listings on the eBay UK marketplace will automatically use the Global Shipping Program for international shipping. Note : The Global Shipping Program is only available for the eBay |
| itemsAwaitingPaymentPreferences | SetItemsAwaitingPaymentPreferencesType | No | This container is included if the seller wishes to change one or more of the items awaiting payment preferences. |
| itemsAwaitingPaymentPreferences.autoRelist | boolean | No | This boolean field is included if the seller wishes to toggle the setting that controls whether or not the line item should be automatically relisted when cancelled. For this field to be set to true , the optInStatus field should also be true . Note : If the line item was part of an auction listing  |
| itemsAwaitingPaymentPreferences.delayBeforeCancellingCommitment | integer | No | This integer field is included if the seller wishes to set or change the number of business days without payment that must elapse before the line item is cancelled. This is a required field if the optInStatus field is true . Note : The supported integer values (representing business days) varies by  |
| itemsAwaitingPaymentPreferences.excludedUsers | array<string> | No | This array is used if the seller wishes to exclude one or more eBay users from the unpaid item assistance mechanism. The seller would need to manually cancel any unpaid line items for all users on this list. This array will not be returned if there are no users on the excluded users list. Note : The |
| itemsAwaitingPaymentPreferences.optInStatus | boolean | No | This boolean field is included if the seller wishes to toggle the setting that controls whether or not the seller is opted into the unpaid item assistance mechanism. If the seller is not opted in, no other fields under itemsAwaitingPaymentPreferences are applicable. |
| itemsAwaitingPaymentPreferences.removeAllExcludedUsers | boolean | No | This boolean field is included and set to true if the seller wishes to remove all eBay users from the current excluded users list. If this field is included and set to true , the excludedUsers array should not be included. |
| outOfStockControlPreference | boolean | No | This boolean field is included if the seller wishes to toggle the setting that controls whether or not the seller is opted into the Out-of-Stock feature. With this feature, a multiple quantity fixed price listing that runs out of stock will be hidden from eBay search but kept alive. Once the sellers |
| purchaseReminderEmailPreferences | boolean | No | This boolean field is included if the seller wishes to toggle the setting that controls whether or not the buyer is expected to provide a shipping phone number upon checkout. Some shipping carriers require the receiver's phone number. |
| requiredShipPhoneNumberPreference | boolean | No | This boolean indicates whether the seller wishes to require phone numbers for shipping or not. |
| shippingCarrierRatePreferences | ShippingCarrierRatePreferencesType | No | This container is included if the seller wishes to add or modify a FedEx, UPS, and/or US Post Office shipping rate type that is available to the seller. Note : This container is only applicable to the eBay US marketplace. |
| shippingCarrierRatePreferences.fedexRateOption | FedexRateOptionEnum | No | This enum is included if the seller wishes to add or modify the FedEx shipping carrier rate. Note : This preference is only applicable to the eBay US marketplace. |
| shippingCarrierRatePreferences.upsRateOption | UPSRateOptionEnum | No | This enum is included if the seller wishes to add or modify the UPS shipping carrier rate. Note : This preference is only applicable to the eBay US marketplace. |

## Response
_No documented response fields._
