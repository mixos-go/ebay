---
title: placeProxyBid
category: Buy_Offer_API
api_name: placeProxyBid
method: POST
path: /bidding/{item_id}/place_proxy_bid
---

**Category:** Buy_Offer_API
**API:** placeProxyBid

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bidding/{item_id}/place_proxy_bid

## API Description
This method uses a user access token to place a proxy bid for the buyer on a specific auction item. The item must offer AUCTION as one of the buyingOptions . To place a bid, you pass in the item ID of the auction as a URI parameter and the buyer's maximum bid amount ( maxAmount ) in the payload. By placing a proxy bid, the buyer is agreeing to purchase the item if they win the auction. After this bid is placed, if someone else outbids the buyer a bid, eBay automatically bids again for the buyer up to the amount of their maximum bid. When the bid exceeds the buyer's maximum bid, eBay will notify them that they have been outbid. To find auctions, you can use the Browse API to search for items and use a filter to return only auction items. For example: /buy/browse/v1/item_summary/search?q=iphone&filter=buyingOptions:{AUCTION} Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| item_id (path) | string | Yes | This path parameter specifies the unique eBay RESTful identifier of an item you want to bid on. This ID is returned by the Browse and Feed Beta API methods. RESTful Item ID Example: v1\|2**********2\|0 For more information about item ID for RESTful APIs, see the Legacy API compatibility section of the |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the buyer is based. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, API Restrictions . |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| maxAmount | Amount | No | The amount of the proxy bid to be placed. This is the maximum amount the buyer is willing to pay for the item. Note: Currency for the bid must be the currency specified by the seller when listing the item. VAT (value added tax) does not need to be added to the proxy bid amount even if VAT applies. |
| maxAmount.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| maxAmount.value | string | No | The monetary amount. |
| userConsent | UserConsent | No | Specifies whether the buyer wants to give their consent to bid on adult-only items. For a buyer to bid on an adult-only item, you must collect their consent using this field, and they must agree to the Terms of Use. For more information about adult-only items on eBay, see Adult-Only items on eBay .  |
| userConsent.adultOnlyItem | boolean | No | The type that defines the fields for buyer consent to bid on adult-only items. This field must be included in the placeProxyBid request and set to true if the buyer is bidding on an adult-only item. For more information about adult-only items on eBay, see Adult-Only items on eBay . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| proxyBidId | string | No | Identifier of the proxy bid created by the request. This indicates that the bid was placed and is not used for anything else. |
