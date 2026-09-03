---
title: getBidding
category: Buy_Offer_API
api_name: getBidding
method: GET
path: /bidding/{item_id}
---

**Category:** Buy_Offer_API
**API:** getBidding

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/bidding/{item_id}

## API Description
This method retrieves the bidding details that are specific to the buyer of the specified auction. This must be an auction where the buyer has already placed a bid. To retrieve the bidding information you use a user access token and pass in the item ID of the auction. You can also retrieve general bidding details about the auction, such as minimum bid price and the count of unique bidders, using the Browse API getItems method. Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| item_id (path) | string | Yes | This path parameter specifies the unique eBay RESTful identifier of an item for which you want the buyer's bidding information. This ID is returned by the Browse and Feed API methods. RESTful Item ID example: v1\|2**********2\|0 For more information about item ID for RESTful APIs, see the Legacy API c |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the buyer is based. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, API Restrictions . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| auctionEndDate | string | No | The date the auction will end. |
| auctionStatus | string | No | An enumeration value that represents the current state of the auction, such as ACTIVE or ENDED . If this value is ENDED and the value of highBidder is true , this indicates the buyer has won the auction. For implementation help, refer to eBay API documentation |
| bidCount | integer | No | The number of proxy bids that have been placed for the auction. |
| currentPrice | Amount | No | The amount of the highest bid, which is the current price of the item. |
| currentPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| currentPrice.value | string | No | The monetary amount. |
| currentProxyBid | ProxyBid | No | The buyer's proxy bid, which is the maxAmount specified in the request. |
| currentProxyBid.maxAmount | Amount | No | The maximum amount the buyer is willing to pay for the item. |
| currentProxyBid.maxAmount.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| currentProxyBid.maxAmount.value | string | No | The monetary amount. |
| currentProxyBid.proxyBidId | string | No | Identifier of a specific proxy bid. |
| highBidder | boolean | No | Indicates if the buyer is the highest bidder. If the value is false , this indicates that either the buyer has not bid on this item or has been out-bid. If this value is true , this indicates the buyer is winning the auction and if the value of auctionStatus is ENDED , this indicates the buyer has w |
| itemId | string | No | The eBay RESTful identifier of an item being bid on, which was submitted in the request. |
| reservePriceMet | boolean | No | This indicates if the reserve price of the item has been met. A reserve price is set by the seller and is the minimum amount the seller is willing to sell the item for. If the highest bid is not equal to or higher than the reserve price when the auction ends, the listing ends and the item is not sol |
| suggestedBidAmounts | array<Amount> | No | The suggested bid amount for the next bid. Note: These are generated suggestions and do not guarantee the buyer will win the bid. This means these suggestions do not take into account the max bid amount of other bidders. The buyer can be outbid even if they submit the highest suggested bid. |
| suggestedBidAmounts.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| suggestedBidAmounts.value | string | No | The monetary amount. |
