---
title: createItemDraft
category: Listing_API
api_name: createItemDraft
method: POST
path: /item_draft/
---

**Category:** Listing_API
**API:** createItemDraft

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/item_draft/

## API Description
This call gives Partners the ability to create an eBay draft of a item for their seller using information from their site. This lets the Partner increase the exposure of items on their site and leverage the eBay user listing experience seamlessly. This experience provides guidance on pricing, aspects, etc. and recommendations that help create a listing that is complete and improves the exposure of the listing in search results. After the listing draft is created, the seller logs into their eBay account and uses the listing experience to finish the listing and publish the item on eBay.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Language (header) | string | No | Use this header to specify the natural language of the seller. For details, see Content-Language in HTTP request headers. Required: For EBAY_CA in French. (Content-Language = fr-CA) |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | Use this header to specify an eBay marketplace ID. For a list of supported sites, see API Restrictions in the Listing API overview. |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryId | string | No | The ID of the leaf category associated with this item. A leaf category is the lowest level in that category and has no children. Note: If you submit both a category ID and an EPID, eBay determines the best category based on the EPID and uses that. The category ID will be ignored. |
| condition | string | No | An enumeration value representing the condition of the item, such as NEW. Note: In all eBay marketplaces, Condition ID 2000 now maps to an item condition of 'Certified Refurbished, and not 'Manufacturer Refurbished'. To list an item as 'Certified Refurbished, a seller must be pre-qualified by eBay f |
| format | string | No | The format of the listing. Valid Values: FIXED_PRICE and AUCTION For implementation help, refer to eBay API documentation |
| pricingSummary | PricingSummary | No | The container that for the information about the cost of an item, such as the price or auction start price. |
| pricingSummary.auctionReservePrice | Amount | No | The minimum amount the seller is willing to sell the item for. If the reserve price isn't met, the item won't be sold. For details, see How reserve prices work. Restrictions: The value is not supported for FIXED_PRICE format. The value format has a maximum of two decimal points. |
| pricingSummary.auctionReservePrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| pricingSummary.auctionReservePrice.value | string | No | The monetary amount, in the currency specified by the currency field. |
| pricingSummary.auctionStartPrice | Amount | No | The minimum amount required for the first bid. Note: The auctionStartPrice value must be less than the auctionReservePrice value. Restrictions: The value is not supported for FIXED_PRICE format. The value format has a maximum of two decimal points. |
| pricingSummary.auctionStartPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| pricingSummary.auctionStartPrice.value | string | No | The monetary amount, in the currency specified by the currency field. |
| pricingSummary.price | Amount | No | The Buy It Now Price for the item. |
| pricingSummary.price.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Restriction: Only the currency of the marketplace is supported. For example, on the US marketplace the only currency supported is USD. For implementation help, refer to eBay API documentation |
| pricingSummary.price.value | string | No | The monetary amount, in the currency specified by the currency field. |
| product | Product | No | The container for the product details of the item. |
| product.aspects | array<Aspect> | No | The list of item aspects that describe the item (such as size, color, capacity, model, brand, etc.) |
| product.aspects.name | string | No | The name of an aspect, such and Brand. |
| product.aspects.values | array<string> | No | A list of potential values for this aspect. |
| product.brand | string | No | The name brand of the item, such as Nike, Apple, etc. |
| product.description | string | No | The description of the item that was created by the seller. This field supports plain text or rich content within HTML tags. Note: Active content is not supported. Active content includes animation or video via JavaScript, Flash, plug-ins, or form actions. Max Length: 500,000 |
| product.epid | string | No | An EPID is the eBay product identifier of a product from the eBay product catalog. Note: If you submit both a category ID and an EPID, eBay determines the best category based on the EPID and uses that. The category ID will be ignored. |
| product.imageUrls | array<string> | No | The image URLs of the item. The first URL will be the primary image, which appears on the View Item page in the eBay listing. The URL can be from the following: The eBay Picture Services (images previously uploaded). A server outside of eBay (self-hosted). For more details, see PictureURL and Introd |
| product.title | string | No | The seller-created title of the item. This should include unique characteristics of the item, such as brand, model, color, size, capacity, etc. For example: Levi's 501 size 10 black jeans |
| charity | Charity | No | This container is used to identify the charitable organization that will receive a percentage of sale proceeds for each sale generated by the listing. This container consists of the charityId field to identify the charitable organization, and the donationPercentage field that will set the percentage |
| charity.donationPercentage | string | No | This field sets the percentage of the purchase price that the charitable organization (identified in the charityId field) will receive for each sale that the listing generates. This field is conditionally required if a seller is planning on donating a percentage of the sale proceeds to a charitable  |
| charity.charityId | string | No | The eBay-assigned unique identifier of the charitable organization that will receive a percentage of the sales proceeds. The charitable organization must be reqistered with the PayPal Giving Fund in order to receive sales proceeds through eBay listings. This field is conditionally required if a sell |

## Response
_No documented response fields._
