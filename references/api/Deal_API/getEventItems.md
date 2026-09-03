---
title: getEventItems
category: Deal_API
api_name: getEventItems
method: GET
path: /event_item
---

**Category:** Deal_API
**API:** getEventItems

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/event_item

## API Description
This method returns a paginated set of event items. The result set contains all event items associated with the specified search criteria and marketplace ID. Restrictions This method can return a maximum of 10,000 items. For a list of supported sites and other restrictions, see API Restrictions . eBay Partner Network: In order to receive a commission for your sales, you must use the URL returned in the itemAffiliateWebUrl field to forward your buyer to the ebay.com site.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_ids (query) | string | No | This query parameter specifies the unique identifiers of the eBay categories for the search. For details see Get Categories for Buy APIs . Maximum Value: 1 |
| delivery_country (query) | string | No | This query parameter allows the response to only return items that can be shipped to the specified country (2-digit ISO code). |
| event_ids (query) | string | Yes | This query parameter specifies the unique identifiers for the eBay event items being retrieved. Use the getEvents method to retrieve event IDs. Maximum Value: 1 |
| limit (query) | string | No | The maximum number of items, from the current result set, returned on a single page. Default: 20 |
| offset (query) | string | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the eBay marketplace. See HTTP request headers for supported marketplace ID values. |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is required to support revenue sharing for eBay Partner Network and to improve the accuracy of shipping and delivery time estimations. For additional information, refer to Use request headers section of the Buying Integration Guide. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| eventItems | array<EventItem> | No | A list of event items that match the search criteria. |
| eventItems.additionalImages | array<Image> | No | The additional images for the event item. |
| eventItems.additionalImages.height | string | No | The height of the image. |
| eventItems.additionalImages.imageUrl | string | No | The relative path to the image location. |
| eventItems.additionalImages.text | string | No | The text associated with the image. |
| eventItems.additionalImages.width | string | No | The width of the image. |
| eventItems.categoryAncestorIds | array<string> | No | The IDs of the ancestors for the primary category. |
| eventItems.categoryId | string | No | The ID of the leaf category for the event item. A leaf category is the lowest level in a category and has no children. |
| eventItems.energyEfficiencyClass | string | No | A string value specifying the Energy Efficiency class. |
| eventItems.eventId | string | No | The unique event identifier associated with the item. |
| eventItems.image | Image | No | The image for the event item. |
| eventItems.image.height | string | No | The height of the image. |
| eventItems.image.imageUrl | string | No | The relative path to the image location. |
| eventItems.image.text | string | No | The text associated with the image. |
| eventItems.image.width | string | No | The width of the image. |
| eventItems.itemAffiliateWebUrl | string | No | The item web URL with affiliate attribution. |
| eventItems.itemGroupId | string | No | The unique identifier for the event item group. This is the parent item ID for the seller-defined variations. Note: This field is returned for multiple-SKU items. |
| eventItems.itemGroupType | string | No | An enumeration value that indicates the type of item group. An item group contains items that have various aspect differences, such as color, size, or storage capacity. For implementation help, refer to eBay API documentation |
| eventItems.itemId | string | No | The unique identifier for the event item. Note: This field is only returned for single-SKU items. |
| eventItems.itemWebUrl | string | No | The web URL for the event item. |
| eventItems.legacyItemId | string | No | The legacy item ID associated with the event item. |
| eventItems.marketingPrice | MarketingPrice | No | The original price for the event item, and the discount amount and percentage. |
| eventItems.marketingPrice.discountAmount | Amount | No | The monetary value of the seller discount. |
| eventItems.marketingPrice.discountAmount.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| eventItems.marketingPrice.discountAmount.value | string | No | The monetary value, in the currency specified by the currency field. |
| eventItems.marketingPrice.discountPercentage | string | No | The percentage of the seller discount based on the value returned in the originalPrice field. |
| eventItems.marketingPrice.originalPrice | Amount | No | The monetary value of the item prior to the discount. |
| eventItems.marketingPrice.originalPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| eventItems.marketingPrice.originalPrice.value | string | No | The monetary value, in the currency specified by the currency field. |
| eventItems.marketingPrice.priceTreatment | string | No | The pricing treatment (discount) that was applied to the price of the item. Note: The pricing treatment affects how and where the discounted price can be displayed. For implementation help, refer to eBay API documentation |
| eventItems.price | Amount | No | The applicable price for the event item. |
| eventItems.price.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| eventItems.price.value | string | No | The monetary value, in the currency specified by the currency field. |
| eventItems.qualifiedPrograms | array<string> | No | A list of programs applicable to the event item. |
| eventItems.shippingOptions | array<ShippingOption> | No | The cost required to ship the event item. |
| eventItems.shippingOptions.shippingCost | Amount | No | The final shipping cost for all items after all discounts are applied. Note: The price does include the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKETPLACE-ID request header specifying the supported mar |
| eventItems.shippingOptions.shippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| eventItems.shippingOptions.shippingCost.value | string | No | The monetary value, in the currency specified by the currency field. |
| eventItems.shippingOptions.shippingCostType | string | No | The class of the shipping cost. Valid Values: FIXED or CALCULATED Code so that your app gracefully handles any future changes to this list. |
| eventItems.title | string | No | The title of the event item. |
| eventItems.unitPrice | Amount | No | The price per unit for the event item. Some European countries require listings for certain types of products to include the price per unit so that buyers can accurately compare prices. For example: "unitPricingMeasure": "100g", "unitPrice": { &nbsp;&nbsp;"value": "7.99", &nbsp;&nbsp;"currency": "GB |
| eventItems.unitPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| eventItems.unitPrice.value | string | No | The monetary value, in the currency specified by the currency field. |
| eventItems.unitPricingMeasure | string | No | The designation used to specify the quantity of the event item, such as size, weight, volume, and count. This helps buyers compare prices. For example, the following tells the buyer that the item is 7.99 per 100 grams. "unitPricingMeasure": "100g", "unitPrice": { &nbsp;&nbsp;"value": "7.99", &nbsp;& |
| href | string | No | The relative path to the current set of results. |
| limit | integer | No | The maximum number of items, from the current result set, returned on a single page. Default: 20 |
| next | string | No | The relative path to the next set of results. |
| offset | integer | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| prev | string | No | The relative path to the previous set of results. |
| total | integer | No | The total number of matches for the specified search criteria. |
