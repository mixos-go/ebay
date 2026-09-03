---
title: getDealItems
category: Deal_API
api_name: getDealItems
method: GET
path: /deal_item
---

**Category:** Deal_API
**API:** getDealItems

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/deal_item

## API Description
This method retrieves a paginated set of deal items. The result set contains all deal items associated with the specified search criteria and marketplace ID. Restrictions This method can return a maximum of 10,000 items. For a list of supported sites and other restrictions, see API Restrictions . eBay Partner Network: In order to receive a commission for your sales, you must use the URL returned in the itemAffiliateWebUrl field to forward your buyer to the ebay.com site.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_ids (query) | string | No | This query parameter specifies the unique identifier of the eBay category for the search. For details see Get Categories for Buy APIs . |
| commissionable (query) | string | No | This query parameter allows the response to filter by commissionable items. If set to true , only commissionable items will be returned in the response. If set to false , commissionable items will not be returned in the response. Note: This filter is currently only supported for the US marketplace. |
| delivery_country (query) | string | No | This query parameter allows the response to only return items that can be shipped to the specified country (2-digit ISO code). |
| limit (query) | string | No | The maximum number of items, from the current result set, returned on a single page. |
| offset (query) | string | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | This header identifies the eBay marketplace. See HTTP request headers for supported marketplace ID values. |
| X-EBAY-C-ENDUSERCTX (header) | string | No | This header is required to support revenue sharing for eBay Partner Network and to improve the accuracy of shipping and delivery time estimations. For additional information, refer to Use request headers section of the Buying Integration Guide. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| dealItems | array<DealItem> | No | A list of deal items that match the search criteria. |
| dealItems.additionalImages | array<Image> | No | The additional images for the deal item. |
| dealItems.additionalImages.height | string | No | The height of the image. |
| dealItems.additionalImages.imageUrl | string | No | The relative path to the image location. |
| dealItems.additionalImages.text | string | No | The text associated with the image. |
| dealItems.additionalImages.width | string | No | The width of the image. |
| dealItems.categoryAncestorIds | array<string> | No | The IDs of the ancestors for the primary category. |
| dealItems.categoryId | string | No | The ID of the leaf category for the deal item. A leaf category is the lowest level in a category and has no children. |
| dealItems.commissionable | boolean | No | A boolean value specifying whether the listing has commission. |
| dealItems.dealAffiliateWebUrl | string | No | The deal associated with the item with affiliate attribution. |
| dealItems.dealEndDate | string | No | The date after which the deal ends. |
| dealItems.dealStartDate | string | No | The date on which the deal starts. |
| dealItems.dealWebUrl | string | No | The web URL for the deal associated with the item. |
| dealItems.energyEfficiencyClass | string | No | A string value specifying the Energy Efficiency class. |
| dealItems.image | Image | No | The primary image for the deal item. |
| dealItems.image.height | string | No | The height of the image. |
| dealItems.image.imageUrl | string | No | The relative path to the image location. |
| dealItems.image.text | string | No | The text associated with the image. |
| dealItems.image.width | string | No | The width of the image. |
| dealItems.itemAffiliateWebUrl | string | No | The item web URL with affiliate attribution. |
| dealItems.itemGroupId | string | No | The unique identifier for the deal item group. This is the parent item ID for the seller-defined variations. Note: This field is returned for multiple-SKU items. |
| dealItems.itemGroupType | string | No | An enumeration value that indicates the type of item group. An item group contains items that have various aspect differences, such as color, size, or storage capacity. For implementation help, refer to eBay API documentation |
| dealItems.itemId | string | No | The unique identifier for the deal item. Note: This field is only returned for single-SKU items. |
| dealItems.itemWebUrl | string | No | The web URL for the deal item. |
| dealItems.legacyItemId | string | No | The legacy item ID associated with the deal item. |
| dealItems.marketingPrice | MarketingPrice | No | The original price for the deal item, and the discount amount and percentage. |
| dealItems.marketingPrice.discountAmount | Amount | No | The monetary value of the seller discount. |
| dealItems.marketingPrice.discountAmount.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| dealItems.marketingPrice.discountAmount.value | string | No | The monetary value, in the currency specified by the currency field. |
| dealItems.marketingPrice.discountPercentage | string | No | The percentage of the seller discount based on the value returned in the originalPrice field. |
| dealItems.marketingPrice.originalPrice | Amount | No | The monetary value of the item prior to the discount. |
| dealItems.marketingPrice.originalPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| dealItems.marketingPrice.originalPrice.value | string | No | The monetary value, in the currency specified by the currency field. |
| dealItems.marketingPrice.priceTreatment | string | No | The pricing treatment (discount) that was applied to the price of the item. Note: The pricing treatment affects how and where the discounted price can be displayed. For implementation help, refer to eBay API documentation |
| dealItems.price | Amount | No | The price for the deal item. Note: The price does include the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKETPLACE-ID request header specifying the supported marketplace (such as EBAY_GB ) to see the VAT |
| dealItems.price.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| dealItems.price.value | string | No | The monetary value, in the currency specified by the currency field. |
| dealItems.qualifiedPrograms | array<string> | No | A list of programs applicable to the item. |
| dealItems.shippingOptions | array<ShippingOption> | No | The cost required to ship the deal item. |
| dealItems.shippingOptions.shippingCost | Amount | No | The final shipping cost for all items after all discounts are applied. Note: The price does include the value-added tax (VAT) for applicable jurisdictions when requested from supported marketplaces. In this case, users must pass the X-EBAY-C-MARKETPLACE-ID request header specifying the supported mar |
| dealItems.shippingOptions.shippingCost.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| dealItems.shippingOptions.shippingCost.value | string | No | The monetary value, in the currency specified by the currency field. |
| dealItems.shippingOptions.shippingCostType | string | No | The class of the shipping cost. Valid Values: FIXED or CALCULATED Code so that your app gracefully handles any future changes to this list. |
| dealItems.title | string | No | The title of the deal item. |
| dealItems.unitPrice | Amount | No | The price per unit for the deal item. Some European countries require listings for certain types of products to include the price per unit so that buyers can accurately compare prices. For example: "unitPricingMeasure": "100g", "unitPrice": { &nbsp;&nbsp;"value": "7.99", &nbsp;&nbsp;"currency": "GBP |
| dealItems.unitPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. Default: The currency of the authenticated user's country. For implementation help, refer to eBay API documentation |
| dealItems.unitPrice.value | string | No | The monetary value, in the currency specified by the currency field. |
| dealItems.unitPricingMeasure | string | No | The designation used to specify the quantity of the deal item, such as size, weight, volume, and count. This helps buyers compare prices. For example, the following tells the buyer that the item is 7.99 per 100 grams. "unitPricingMeasure": "100g", "unitPrice": { &nbsp;&nbsp;"value": "7.99", &nbsp;&n |
| href | string | No | The relative path to the current set of results. |
| limit | integer | No | The maximum number of items, from the current result set, returned on a single page. Default: 20 |
| next | string | No | The relative path to the next set of results. |
| offset | integer | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| prev | string | No | The relative path to the previous set of results. |
| total | integer | No | The total number of matches for the search criteria. |
