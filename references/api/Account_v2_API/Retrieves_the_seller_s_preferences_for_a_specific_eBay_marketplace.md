---
title: Retrieves_the_seller_s_preferences_for_a_specific_eBay_marketplace
category: Account_v2_API
api_name: Retrieves_the_seller_s_preferences_for_a_specific_eBay_marketplace
method: GET
path: /user_preferences
---

**Category:** Account_v2_API
**API:** Retrieves_the_seller_s_preferences_for_a_specific_eBay_marketplace

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/user_preferences

## API Description
Retrieves the seller's preferences for a specific eBay marketplace.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| fieldgroups (query) | string | No | The fieldgroups query parameter specifies the type of seller preferences to retrieve. If fieldgroups = ALL or is omitted, all the supported seller preferences are returned. To retrieve specific seller preferences, include the fieldgroups parameter and specify one or more values, with each value deli |
| X-EBAY-C-MARKETPLACE-ID (header) | MarketplaceIdEnum | Yes | This required header sets the eBay marketplace where the request is processed. For the full list of eBay marketplace values, see the MarketplaceIdEnum type. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| combinedPaymentPreferences | CombinedPaymentPreferencesType | No | This container returns the combined payment preferences when the COMBINED_PAYMENT value is included through the fieldgroups query parameter or when fieldgroups = ALL . It indicates if the seller allows multiple line items from the same buyer to be combined. |
| combinedPaymentPreferences.combinedPaymentOption | CombinedPaymentOptionEnum | No | This enum type defines the available options for handling combined payments when a seller allows multiple line items from the same buyer to be paid for with a single payment. See CombinedPaymentOptionEnum for a description of each value. |
| dispatchCutoffTimePreference | DispatchCutoffTimePreferencesType | No | This container is returned when the DISPATCH_CUTOFF_TIME value is included through the fieldgroups query parameter or when fieldgroups = ALL . |
| dispatchCutoffTimePreference.cutoffTime | string | No | This field indicates the dispatch cut-off time in Zulu format ( HH:mm:ss.SSSZ ) - 24-hour format with milliseconds and Z timezone indicator. Note: Despite the Z that is returned in the timestamp, the cut-off time is actually based on the default timezone of the eBay marketplace for the seller. Note: |
| emailShipmentTrackingNumberPreference | boolean | No | This boolean field indicates whether or not the seller’s account is configured to automatically send an email to buyers with the shipment tracking number for an order. |
| endOfAuctionEmailPreferences | EndOfAuctionEmailPreferencesType | No | This container allows sellers to customize the email sent to buyers immediately after an auction listing is won. |
| endOfAuctionEmailPreferences.emailCustomized | boolean | No | This boolean field indicates whether or not the seller is using a customized email to send to winning bidders. |
| endOfAuctionEmailPreferences.logoCustomized | boolean | No | This boolean field indicates whether or not the seller is using a customized logo in the emails that are sent to winning bidders. |
| endOfAuctionEmailPreferences.logoType | EndOfAuctionLogoTypeEnum | No | This enum indicates the type of logo that is used in the email that is sent to winning bidders. See EndOfAuctionLogoTypeEnum type for descriptions of the different logo types. |
| endOfAuctionEmailPreferences.logoUrl | string | No | This field shows the URL path to a seller’s custom logo image that is being used in the email sent to winning bidders. This field is only returned if the seller is using a customized logo in emails. |
| endOfAuctionEmailPreferences.templateText | string | No | This field shows the body text that is being used if the seller is sending customized emails to winning bidders. The template text has a maximum limit of 1000 characters. |
| endOfAuctionEmailPreferences.textCustomized | boolean | No | This boolean field indicates whether or not the seller is using customized text in the emails that are sent to winning bidders. |
| globalShippingProgramListingPreference | boolean | No | This boolean field indicates whether or not the seller’s new listings on the eBay marketplace will automatically use the Global Shipping Program for international shipping. This field is returned when the GLOBAL_SHIPPING_PROGRAM value is included through the fieldgroups query parameter or when field |
| itemsAwaitingPaymentPreferences | GetItemsAwaitingPaymentPreferencesType | No | This container shows the seller’s preferences for automatically handling unpaid line items. |
| itemsAwaitingPaymentPreferences.autoRelist | boolean | No | This boolean indicates if the item should be automatically relisted. |
| itemsAwaitingPaymentPreferences.delayBeforeCancellingCommitment | integer | No | This integer indicates the delay in days before cancelling the buyer&#x27;s commitment. |
| itemsAwaitingPaymentPreferences.excludedUsers | array<string> | No | This string returns the list of sellers excluded from unpaid item assistance. |
| itemsAwaitingPaymentPreferences.optInStatus | boolean | No | This boolean indicates if the unpaid item assistance is opted in. |
| offerGlobalShippingProgramPreference | boolean | No | This boolean field indicates whether or not the seller is opted into the Global Shipping Program on the eBay marketplace. Note : The Global Shipping Program is only available for the eBay UK marketplace. |
| outOfStockControlPreference | boolean | No | This boolean field indicates whether or not the seller is opted into the Out-of-Stock feature. With this feature, a multiple quantity fixed price listing that runs out of stock will be hidden from eBay search but kept alive. Once the sellers add quantity to the listing, the listing will become activ |
| overrideGspServiceWithIntlServicePreference | boolean | No | This boolean field indicates whether or not the seller specifies an international shipping service to a particular country for a given listing, the specified service will take precedence and be the listing's default international shipping option for buyers in that country, rather than the Global Shi |
| pickupDropoffSellerPreference | boolean | No | This boolean field indicates whether or not the seller is opted into the Click & Collect feature. Note : The Click & Collect feature is only available on the eBay UK, Australia, and Germany marketplaces. |
| purchaseReminderEmailPreferences | boolean | No | This boolean field indicates whether or not the seller’s account is configured to have eBay send occasional purchase reminder emails for unpaid line items. |
| requiredShipPhoneNumberPreference | boolean | No | This boolean field indicates whether or not the buyer is required to provide a shipping phone number during checkout. |
| sellerExcludeShipToLocationPreferences | SellerExcludeShipToLocationPreferencesType | No | This container shows the list of locations that the seller does not ship to. This list of shipping locations can only be updated in My eBay through Shipping Preferences and not with the setUserPreferences method. |
| sellerExcludeShipToLocationPreferences.excludeShipToLocations | array<string> | No | This array shows the list of locations that the seller does not ship to. Excluded locations may include continents and large geographical areas. For example, 'Middle East', individual countries represented by two-letter codes, or special locations within a country such as 'Alaska/Hawaii' or 'PO Box' |
| sellerProfilePreferences | SellerProfilePreferencesType | No | This container is returned when the SELLER_PROFILE value is included through the fieldgroups query parameter or when fieldgroups = ALL . |
| sellerProfilePreferences.sellerProfileOptedIn | boolean | No | This boolean indicates whether the seller has opted in to seller profiles. |
| shippingCarrierRatePreferences | ShippingCarrierRatePreferencesType | No | This container indicates the FedEx, UPS, and US Post Office shipping rate types that are available to the seller. This container is returned when the SHIPPING_CARRIER_RATE value is included through the fieldgroups query parameter or when fieldgroups = ALL . Note : This container is only applicable t |
| shippingCarrierRatePreferences.fedexRateOption | FedexRateOptionEnum | No | This enum is included if the seller wishes to add or modify the FedEx shipping carrier rate. Note : This preference is only applicable to the eBay US marketplace. |
| shippingCarrierRatePreferences.upsRateOption | UPSRateOptionEnum | No | This enum is included if the seller wishes to add or modify the UPS shipping carrier rate. Note : This preference is only applicable to the eBay US marketplace. |
