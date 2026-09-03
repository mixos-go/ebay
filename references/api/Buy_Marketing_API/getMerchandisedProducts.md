---
title: getMerchandisedProducts
category: Buy_Marketing_API
api_name: getMerchandisedProducts
method: GET
path: /merchandised_product
---

**Category:** Buy_Marketing_API
**API:** getMerchandisedProducts

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/merchandised_product

## API Description
This method returns an array of products based on the category and metric specified. This includes details of the product, such as the eBay product ID (EPID), title, and user reviews and ratings for the product. You can use the epid returned by this method in the Browse API search method to retrieve items for this product. Restrictions To test getMerchandisedProducts in Sandbox, you must use category ID 9355 and the response will be mock data. For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| aspect_filter (query) | string | No | This value specifies the aspect name/value pairs used to further refine product results. For example: &nbsp;&nbsp;&nbsp; /buy/marketing/v1_beta/merchandised_product?category_id=31388&metric_name=BEST_SELLING&aspect_filter=Brand:Canon You can use the Browse API search method with the fieldgroups=ASPE |
| category_id (query) | string | Yes | This query parameter limits the products returned to a specific eBay category. The list of eBay category IDs is not published and category IDs are not all the same across all the eBay maketplace. You can use the following techniques to find a category by site: Use the Category Changes page . Use the |
| limit (query) | string | No | This value specifies the maximum number of products to return in a result set. Note: Maximum value means the method will return up to that many products per set, but it can be less than this value. If the number of products found is less than this value, the method will return all of the products ma |
| metric_name (query) | string | Yes | This value filters the result set by the specified metric. Only products in this metric are returned. Note: Currently, the only metric supported is BEST_SELLING . Default: BEST_SELLING Maximum: 1 Required: 1 |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| merchandisedProducts | array<MerchandisedProduct> | No | An array of containers for the products. |
| merchandisedProducts.averageRating | string | No | The average rating for the product based on eBay user ratings. |
| merchandisedProducts.epid | string | No | The eBay product identifier of a product from the eBay product catalog. You can use this value in the Browse API search method to retrieve items for this product. |
| merchandisedProducts.image | Image | No | The container for the product image. |
| merchandisedProducts.image.height | integer | No | Reserved for future use. |
| merchandisedProducts.image.imageUrl | string | No | The URL of the image. |
| merchandisedProducts.image.width | integer | No | Reserved for future use. |
| merchandisedProducts.marketPriceDetails | array<MarketPriceDetail> | No | An array of containers for the product market price details, such as condition and market price. |
| merchandisedProducts.marketPriceDetails.conditionGroup | string | No | The name for the condition of the product. For example: NEW |
| merchandisedProducts.marketPriceDetails.conditionIds | array<string> | No | An array of condition identifiers for the product. |
| merchandisedProducts.marketPriceDetails.estimatedStartPrice | Amount | No | The lowest priced active item for this product on eBay. |
| merchandisedProducts.marketPriceDetails.estimatedStartPrice.currency | string | No | The three-letter ISO 4217 code representing the currency of the amount in the value field. For implementation help, refer to eBay API documentation |
| merchandisedProducts.marketPriceDetails.estimatedStartPrice.value | string | No | The monetary amount, in the currency specified by the currency field. |
| merchandisedProducts.ratingAspects | array<RatingAspect> | No | An array of containers for ratings of the product aspects, such as "Is it a good value". |
| merchandisedProducts.ratingAspects.count | integer | No | The number of eBay users that rated the product on this aspect. |
| merchandisedProducts.ratingAspects.description | string | No | The name of the rating aspect. Camping tent examples: Is it lightweight? or Is it easy to set up? |
| merchandisedProducts.ratingAspects.name | string | No | The answer or value of the rating aspect. Camping tent examples: Lightweight or Easy to set up |
| merchandisedProducts.ratingAspects.ratingAspectDistributions | array<RatingAspectDistribution> | No | The container for the details of the aspect rating. The details show the aspect rating value, usually TRUE or FALSE and the user count and percentage. |
| merchandisedProducts.ratingAspects.ratingAspectDistributions.count | integer | No | The number of eBay users that choose this rating aspect value. |
| merchandisedProducts.ratingAspects.ratingAspectDistributions.percentage | string | No | The percentage of the aspect rating value. ratingAspectDistributions.percentage = ratingAspectDistributions.count / ratingAspects.count |
| merchandisedProducts.ratingAspects.ratingAspectDistributions.value | string | No | The rating aspect. For example: TRUE or FALSE |
| merchandisedProducts.ratingCount | integer | No | The total number of eBay users that rated the product. |
| merchandisedProducts.reviewCount | integer | No | The total number of eBay users that wrote a review for the product. |
| merchandisedProducts.title | string | No | The title of the product. |
| warnings | array<Error> | No | The container with all the warnings for the input request. |
| warnings.category | string | No | This string value indicates the error category. There are three categories of errors: request errors, application errors, and system errors. |
| warnings.domain | string | No | The name of the primary system where the error occurred. This is relevant for application errors. |
| warnings.errorId | integer | No | A unique code that identifies the particular error or warning that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | An array of reference IDs that identify the specific request elements most closely associated to the error or warning, if any. |
| warnings.longMessage | string | No | A detailed description of the condition that caused the error or warning, and information on what to do to correct the problem. |
| warnings.message | string | No | A description of the condition that caused the error or warning. |
| warnings.outputRefIds | array<string> | No | An array of reference IDs that identify the specific response elements most closely associated to the error or warning, if any. |
| warnings.parameters | array<ErrorParameter> | No | An array of warning and error messages that return one or more variables contextual information about the error or warning. This is often the field or value that triggered the error or warning. |
| warnings.parameters.name | string | No | This is the name of input field that caused an issue with the call request. |
| warnings.parameters.value | string | No | This is the actual value that was passed in for the element specified in the name field. |
| warnings.subdomain | string | No | The name of the subdomain in which the error or warning occurred. |
