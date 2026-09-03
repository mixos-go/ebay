---
title: search
category: Marketplace_Insights_API
api_name: search
method: GET
path: /item_sales/search
---

**Category:** Marketplace_Insights_API
**API:** search

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/item_sales/search

## API Description
(Limited Release) This method searches for sold eBay items by various URI query parameters and retrieves the sales history of the items for the last 90 days. You can search by keyword, category, eBay product ID (ePID), or GTIN, or a combination of these. This method also supports the following: Filtering by the value of one or multiple fields, such as listing format, item condition, price range, location, and more. For the fields supported by this method, see the filter parameter. Retrieving the refinements (metadata) of an item , such as item aspects (color, brand), condition, category, etc. using the fieldgroups parameter. Filtering by item aspects and other refinements using the aspect_filter parameter. Creating aspects histograms, which enables shoppers to drill down in each refinement narrowing the search results. For details and examples of these capabilities, see Browse API in the Buying Integration Guide. Pagination and sort controls There are pagination controls (limit and offset fields) and sort query parameters that control/sort the data that is returned. By default, the results are sorted by &quot;Best Match&quot;. For more information about Best Match, see the eBay help page Best Match. URLs for this method Production URL: https://api.ebay.com/buy/marketplace_insights/v1_beta/item_sales/ Sandbox URL: https://api.sandbox.ebay.com/buy/marketplace_insights/v1_beta/item_sales/ Request headers You will want to use the X-EBAY-C-ENDUSERCTX request header with this method. If you are an eBay Network Partner you must use affiliateCampaignId=ePNCampaignId,affiliateReferenceId=referenceId in the header in order to be paid for selling eBay items on your site . For details see, Request headers in the Buy APIs Overview. URL Encoding for Parameters Query parameter values need to be URL encoded. For details, see URL encoding query parameter values. Restrictions For a list of supported sites and other restrictions, see API Restrictions.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| aspect_filter (query) | string | No | This field lets you filter by item aspects. The aspect name/value pairs and category, which is required, is used to limit the results to specific aspects of the item. For example, in a clothing category one aspect pair would be Color/Red. The results are returned in the refinement container. For exa |
| category_ids (query) | string | No | The category ID is required and is used to limit the results. For example, if you search for 'shirt' the result set will be very large. But if you also include the category ID 137084, the results will be limited to 'Men's Athletic Apparel'. For example: /buy/marketplace-insights/v1_beta/item_sales/s |
| epid (query) | string | No | The ePID is the eBay product identifier of a product from the eBay product catalog. This field limits the results to only items in the specified ePID. /buy/marketplace-insights/v1_beta/item_sales/search?epid=241986085&amp;category_ids=168058 You can use the product_summary/search method in the Catal |
| fieldgroups (query) | string | No | This field lets you control what is to be returned in the response and accepts a comma separated list of values. The default is MATCHING_ITEMS, which returns the items that match the keyword or category specified. The other values return data that can be used to create histograms. For code examples  |
| filter (query) | string | No | This field supports multiple field filters that can be used to limit/customize the result set. The following lists the supported filters. For details and examples for all the filters, see Buy API Field Filters. buyingOptions conditionIds conditions itemLocationCountry lastSoldDate price priceCurrenc |
| gtin (query) | string | No | This field lets you search by the Global Trade Item Number of the item as defined by https://www.gtin.info. This can be a UPC (Universal Product Code), EAN (European Article Number), or an ISBN (International Standard Book Number) value. /buy/marketplace-insights/v1_beta/item_sales/search?gtin=24198 |
| limit (query) | string | No | The number of items, from the result set, returned in a single page. Default: 50 Maximum number of items per page (limit): 200 Maximum number of items in a result set: 10,000 |
| offset (query) | string | No | Specifies the number of items to skip in the result set. This is used with the limit field to control the pagination of the output. If offset is 0 and limit is 10, the method will retrieve items 1-10 from the list of items returned, if offset is 10 and limit is 10, the method will retrieve items 11  |
| q (query) | string | No | A string consisting of one or more keywords that are used to search for items on eBay. The keywords are handled as follows: If the keywords are separated by a comma, it is treated as an AND. In the following example, the query returns items that have iphone AND ipad. /buy/marketplace-insights/v1_bet |
| sort (query) | string | No | This field specifies the order and the field name to use to sort the items. To sort in descending order use - before the field name. Currently, you can only sort by price (in ascending or descending order). If no sort parameter is submitted, the result set is sorted by &quot;Best Match&quot;. The fo |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. The following example returns items 1 thru 5 from the list of items found. https://api.ebay.com/buy/marketplace_insights/v1_beta/item_sales/search?q=shirt&amp;&amp;limit=5&amp;offset=0 |
| itemSales | array<ItemSales> | No | The type that defines the fields for a paginated result set of the sold items. The response consists of 0 or more sequenced result sets where each result sets has 0 or more items. Note: For items with multiple quantities that might result in multiple transactions, and items with the SELLER_DEFINED_V |
| itemSales.additionalImages | array<Image> | No | An array of containers with the URLs for the images that are in addition to the primary image. The primary image is returned in the image.imageUrl field. |
| itemSales.additionalImages.height | integer | No | Reserved for future use. |
| itemSales.additionalImages.imageUrl | string | No | The URL of the image. |
| itemSales.additionalImages.width | integer | No | Reserved for future use. |
| itemSales.adultOnly | boolean | No | This indicates if the item is for adults only. For more information about adult-only items on eBay, see Adult items policy for sellers and Adult-Only items on eBay for buyers. |
| itemSales.bidCount | integer | No | This integer value indicates the total number of bids that have been placed for an auction item. This field is only returned for auction items. |
| itemSales.buyingOptions | array<string> | No | A comma separated list of the purchase options available for the item, such as FIXED_PRICE, AUCTION. FIXED_PRICE - Returned for fixed-price items (non-auction) AUCTION - Returned for auction items without Buy It Now feature FIXED_PRICE and AUCTION - Returned for auction items enabled with the Buy It |
| itemSales.categories | array<Category> | No | This container returns the primary category ID of the item, as well as the secondary category if the item was listed in two categories. |
| itemSales.categories.categoryId | string | No | The unique identifier of the primary item category of the item, as well as the secondary item category if item was listed in two categories. |
| itemSales.condition | string | No | The text describing the condition of the item, such as New or Used. For a list of condition names, see Item Condition IDs and Names. Code so that your app gracefully handles any future changes to this list. |
| itemSales.conditionId | string | No | The identifier of the condition of the item. For example, 1000 is the identifier for NEW. For a list of condition names and IDs, see Item Condition IDs and Names. Code so that your app gracefully handles any future changes to this list. |
| itemSales.epid | string | No | An ePID is the eBay product identifier of a product from the eBay product catalog. This indicates the product in which the item belongs. |
| itemSales.image | Image | No | The URL to the primary image of the item. |
| itemSales.image.height | integer | No | Reserved for future use. |
| itemSales.image.imageUrl | string | No | The URL of the image. |
| itemSales.image.width | integer | No | Reserved for future use. |
| itemSales.itemAffiliateWebUrl | string | No | The URL to the View Item page of the item, which includes the affiliate tracking ID. This field is only returned if the eBay partner enables affiliate tracking for the item by including the X-EBAY-C-ENDUSERCTX request header in the method. |
| itemSales.itemGroupHref | string | No | The HATEOAS reference of the parent page of the item group. An item group is an item that has various aspect differences, such as color, size, storage capacity, etc. Note: This field is returned only for item groups. |
| itemSales.itemGroupType | string | No | Indicates the item group type. An item group is an item that has various aspect differences, such as color, size, storage capacity, etc. Currently, only the SELLER_DEFINED_VARIATIONS group type is supported and indicates that this is an item group created by the seller. Note: This field is returned  |
| itemSales.itemHref | string | No | The URI of the item. |
| itemSales.itemId | string | No | The unique RESTful identifier of the item. |
| itemSales.itemLocation | ItemLocation | No | This container returns the postal code and country of the location of the item. |
| itemSales.itemLocation.addressLine1 | string | No | The first line of the street address. |
| itemSales.itemLocation.addressLine2 | string | No | The second line of the street address. This field may contain such values as an apartment or suite number. |
| itemSales.itemLocation.city | string | No | The city in which the item is located. |
| itemSales.itemLocation.country | string | No | The two-letter ISO 3166 standard code that indicates the country in which the item is located. For implementation help, refer to eBay API documentation |
| itemSales.itemLocation.county | string | No | The county in which the item is located. |
| itemSales.itemLocation.postalCode | string | No | The postal code (or zip code in US) where the item is located. Note: Beginning in late January 2020, the displayed postal code will be masked to all users. Different countries will mask postal/zip codes in slightly different ways, but an example would be 951**. |
| itemSales.itemLocation.stateOrProvince | string | No | The state or province in which the item is located. |
| itemSales.itemWebUrl | string | No | The URL to the View Item page of the item. |
| itemSales.lastSoldDate | string | No | The date the last item was purchased within the last 90 days. The totalSoldQuantity returns the total number of items that were sold. This field returns the date the last item in that group was sold. |
| itemSales.lastSoldPrice | ConvertedAmount | No | The sold price of the last item purchased within the last 90 days. The totalSoldQuantity returns the total number of items that were sold. This field returns the date the last item in that group was sold.. |
| itemSales.lastSoldPrice.convertedFromCurrency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the convertedFromValue field. This value represents the pre-conversion currency. For implementation help, refer to eBay API documentation |
| itemSales.lastSoldPrice.convertedFromValue | string | No | The monetary amount before any conversion is performed, in the currency specified by the convertedFromCurrency field. The value field contains the converted amount of this value, in the currency specified by the currency field. |
| itemSales.lastSoldPrice.currency | string | No | A three-letter ISO 4217 code that indicates the currency of the amount in the value field. This value represents the post-conversion currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| itemSales.lastSoldPrice.value | string | No | The monetary value in the currency specified in the currency field. |
| itemSales.seller | Seller | No | This container returns basic information about the seller of the item, such as name, feedback score, etc. |
| itemSales.seller.feedbackPercentage | string | No | The percentage of the total positive feedback. |
| itemSales.seller.feedbackScore | integer | No | The feedback score of the seller. This value is based on the ratings from eBay members that bought items from this seller. |
| itemSales.seller.username | string | No | The username created by the seller for use on eBay. |
| itemSales.thumbnailImages | array<Image> | No | An array of thumbnail images for the item. |
| itemSales.thumbnailImages.height | integer | No | Reserved for future use. |
| itemSales.thumbnailImages.imageUrl | string | No | The URL of the image. |
| itemSales.thumbnailImages.width | integer | No | Reserved for future use. |
| itemSales.title | string | No | The seller-created title of the item. Maximum Length: 80 characters |
| itemSales.totalSoldQuantity | integer | No | The total number of this item that have been sold. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length: 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length: 2048 |
| refinement | Refinement | No | The container for all the search refinements. |
| refinement.aspectDistributions | array<AspectDistribution> | No | A array of containers for the all the aspect refinements. |
| refinement.aspectDistributions.aspectValueDistributions | array<AspectValueDistribution> | No | An array of containers for the various values of the aspect and the match count and a HATEOAS reference ( refinementHref) for this aspect. |
| refinement.aspectDistributions.aspectValueDistributions.localizedAspectValue | string | No | The value of an aspect. For example, Red is a value for the aspect Color. |
| refinement.aspectDistributions.aspectValueDistributions.matchCount | integer | No | The number of items with this aspect. |
| refinement.aspectDistributions.aspectValueDistributions.refinementHref | string | No | A HATEOAS reference for this aspect. |
| refinement.aspectDistributions.localizedAspectName | string | No | Name of an aspect, such as Brand, Color, etc. |
| refinement.buyingOptionDistributions | array<BuyingOptionDistribution> | No | A array of containers for the all the buying option refinements. |
| refinement.buyingOptionDistributions.buyingOption | string | No |  |
| refinement.buyingOptionDistributions.matchCount | integer | No | The number of items having this buying option. |
| refinement.buyingOptionDistributions.refinementHref | string | No | The HATEOAS reference for this buying option. |
| refinement.categoryDistributions | array<CategoryDistribution> | No | A array of containers for the all the category refinements. |
| refinement.categoryDistributions.categoryId | string | No | The identifier of the category. |
| refinement.categoryDistributions.categoryName | string | No | The name of the category, such as Baby &amp; Toddler Clothing. |
| refinement.categoryDistributions.matchCount | integer | No | The number of items in this category. |
| refinement.categoryDistributions.refinementHref | string | No | The HATEOAS reference of this category. |
| refinement.conditionDistributions | array<ConditionDistribution> | No | A array of containers for the all the condition refinements. |
| refinement.conditionDistributions.condition | string | No | The text describing the condition of the item, such as New or Used. For a list of condition names, see ConditionEnum. Code so that your app gracefully handles any future changes to this list. |
| refinement.conditionDistributions.conditionId | string | No | The identifier of the condition. For example, 1000 is the identifier for NEW. |
| refinement.conditionDistributions.matchCount | integer | No | The number of items having the condition. |
| refinement.conditionDistributions.refinementHref | string | No | The HATEOAS reference of this condition. |
| refinement.dominantCategoryId | string | No | The identifier of the category that most of the items are part of. |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0. |
