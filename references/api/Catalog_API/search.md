---
title: search
category: Catalog_API
api_name: search
method: GET
path: /product_summary/search
---

**Category:** Catalog_API
**API:** search

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/product_summary/search

## API Description
This method searches for and retrieves summaries of one or more products in the eBay catalog that match the search criteria provided by a seller. The seller can use the summaries to select the product in the eBay catalog that corresponds to the item that the seller wants to offer for sale. When a corresponding product is found and adopted by the seller, eBay will use the product information to populate the item listing. The criteria supported by search include keywords, product categories, and category aspects. To see the full details of a selected product, use the getProduct call. In addition to product summaries, this method can also be used to identify refinements , which help you to better pinpoint the product you're looking for. A refinement consists of one or more aspect values and a count of the number of times that each value has been used in previous eBay listings. An aspect is a property (e.g. color or size) of an eBay category, used by sellers to provide details about the items they're listing. The refinement container is returned when you include the fieldGroups query parameter in the request with a value of ASPECT_REFINEMENTS or FULL . Example A seller wants to find a product that is "gray" in color, but doesn't know what term the manufacturer uses for that color. It might be Silver , Brushed Nickel , Pewter , or even Grey . The returned refinement container identifies all aspects that have been used in past listings for products that match your search criteria, along with all of the values those aspects have taken, and the number of times each value was used. You can use this data to present the seller with a histogram of the values of each aspect. The seller can see which color values have been used in the past, and how frequently they have been used, and selects the most likely value or values for their product. You issue the search method again with those values in the aspect_filter parameter to narrow down the collection of products returned by the call. Although all query parameters are optional, this method must include at least the q parameter, or the category_ids , gtin , or mpn parameter with a valid value. If you provide more than one of these parameters, they will be combined with a logical AND to further refine the returned collection of matching products. Note: This method requires that certain special characters in the query parameters be percent-encoded: &nbsp;&nbsp;&nbsp;&nbsp; (space) = %20 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; , = %2C &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; : = %3A &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [ = %5B &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ] = %5D &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; { = %7B &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; | = %7C &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; } = %7D This requirement applies to all query parameter values. However, for readability, method examples and samples in this documentation will not use the encoding. This method returns product summaries rather than the full details of the products. To retrieve the full details of a product, use the getProduct method with an ePID.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | No | This method also uses the X-EBAY-C-MARKETPLACE-ID header to identify the seller's eBay marketplace. It is required for all supported marketplaces , except EBAY_US, which is the default. |
| aspect_filter (query) | string | No | An eBay category and one or more aspects of that category, with the values that can be used to narrow down the collection of products returned by this call. Aspects are product attributes that can represent different types of information for different products. Every product has aspects, but differe |
| category_ids (query) | string | No | Important: Currently, only the first category_id value is accepted. One or more comma-separated category identifiers for narrowing down the collection of products returned by this call. Note: This parameter requires a valid category ID value. You can use the Taxonomy API's getCategorySuggestions met |
| fieldgroups (query) | string | No | The type of information to return in the response. Important: This parameter may not produce valid results if you also provide more than one value for the category_ids parameter. It is recommended that you avoid using this combination. Valid Values: ASPECT_REFINEMENTS &mdash; This returns the refine |
| gtin (query) | string | No | A string consisting of one or more comma-separated Global Trade Item Numbers (GTINs) that identify products to search for. Currently the GTIN values can include EAN, ISBN, and UPC identifier types. Note: Although all query parameters are optional, this method must include at least the q parameter, o |
| limit (query) | string | No | The number of product summaries to return. This is the result set , a subset of the full collection of products that match the search or filter criteria of this call. Maximum: 200 Default: 50 |
| mpn (query) | string | No | A string consisting of one or more comma-separated Manufacturer Part Numbers (MPNs) that identify products to search for. This method will return all products that have one of the specified MPNs. MPNs are defined by manufacturers for their own products, and are therefore certain to be unique only wi |
| offset (query) | string | No | This parameter is reserved for internal or future use. |
| q (query) | string | No | A string consisting of one or more keywords to use to search for products in the eBay catalog. Note: This method searches the following product record fields: title , description , brand , and aspects.localizedName , which do not include product IDs. Wildcard characters (e.g. * ) are not allowed. Th |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | This field is reserved for internal or future use. search method request that produced this result set. --> |
| limit | integer | No | The number of product summaries returned in the response. This is the result set , a subset of the full collection of products that match the search or filter criteria of this call. If the limit query parameter was included in the request, this field will have the same value. Default: 50 |
| next | string | No | This field is reserved for internal or future use. Returned only if there are more product records to retrieve from the current collection of matching products, this field contains the search call URI for the next result set. For example, the following URI returns records 41 thru 50 from the collect |
| offset | integer | No | This field is reserved for internal or future use. offset query parameter was included in the request, this field will have the same value. The offset value is used in conjunction with the limit value to control the pagination of the output. For example, if offset is set to 30 and limit is set to 10 |
| prev | string | No | This field is reserved for internal or future use. Not returned if the currently returned result set is the first set of product records from the current collection of matching products. This field contains the search call URI for the previous result set. For example, the following URI returns produ |
| productSummaries | array<ProductSummary> | No | Returned if the fieldGroups query parameter was omitted from the request, or if it was included with a value of MATCHING_PRODUCTS or FULL . This container provides an array of product summaries in the current result set for products that match the combination of the q , category_ids , and aspect_fil |
| productSummaries.additionalImages | array<Image> | No | Contains information about additional images associated with this product. For the primary image, see the image container. |
| productSummaries.additionalImages.height | integer | No | The height of the image in pixels. |
| productSummaries.additionalImages.imageUrl | string | No | The eBay Picture Services (EPS) URL of the image. |
| productSummaries.additionalImages.width | integer | No | The width of the image in pixels. |
| productSummaries.aspects | array<Aspect> | No | Contains an array of the category aspects and their values that are associated with this product. |
| productSummaries.aspects.localizedName | string | No | The localized name of this category aspect. |
| productSummaries.aspects.localizedValues | array<string> | No | A list of the localized values of this category aspect. |
| productSummaries.brand | string | No | The manufacturer's brand name for this product. |
| productSummaries.ean | array<string> | No | A list of all European Article Numbers (EANs) that identify this product. |
| productSummaries.epid | string | No | The eBay product ID of this product. |
| productSummaries.gtin | array<string> | No | A list of all GTINs that identify this product. This includes all of the values returned in the ean , isbn , and upc fields. |
| productSummaries.image | Image | No | Contains information about the primary image of this product. For more images of this product, see the additionalImages container. |
| productSummaries.image.height | integer | No | The height of the image in pixels. |
| productSummaries.image.imageUrl | string | No | The eBay Picture Services (EPS) URL of the image. |
| productSummaries.image.width | integer | No | The width of the image in pixels. |
| productSummaries.isbn | array<string> | No | A list of all International Standard Book Numbers (ISBNs) that identify this product. |
| productSummaries.mpn | array<string> | No | A list of all Manufacturer Product Number (MPN) values that the manufacturer uses to identify this product. |
| productSummaries.productHref | string | No | The URI of the getProduct call request that retrieves this product's details. |
| productSummaries.productWebUrl | string | No | The URL for this product's eBay product page. |
| productSummaries.title | string | No | The title of this product on eBay. |
| productSummaries.upc | array<string> | No | A list of Universal Product Codes (UPCs) that identify this product. |
| refinement | Refinement | No | Returned only if the fieldGroups query parameter was included in the request with a value of ASPECT_REFINEMENTS or FULL . An aspect is a property of a category, used by sellers to provide details about the items they're listing. For example, the Cell Phones &amp; Smartphones category (#9355) include |
| refinement.aspectDistributions | array<AspectDistribution> | No | Contains information about one or more aspects that are associated with the category identified by dominantCategoryId . |
| refinement.aspectDistributions.aspectValueDistributions | array<AspectValueDistribution> | No | Contains information about one or more values of the category aspect identified by localizedAspectName . |
| refinement.aspectDistributions.aspectValueDistributions.localizedAspectValue | string | No | The localized value of the category aspect identified by refinement.aspectDistributions.localizedAspectName . |
| refinement.aspectDistributions.aspectValueDistributions.matchCount | integer | No | The number of times the value of localizedAspectValue has been used for eBay product listings. By comparing this quantity to the matchCount for other values of the same aspect, you can present a histogram of the values to sellers, who can use that information to select which aspect value is most app |
| refinement.aspectDistributions.aspectValueDistributions.refinementHref | string | No | A HATEOAS reference that further refines the search with this particular localizedAspectValue . |
| refinement.aspectDistributions.localizedAspectName | string | No | The localized name of an aspect that is associated with the category identified by dominantCategoryId . |
| refinement.dominantCategoryId | string | No | The ID of the category that eBay determines is most likely to cover the products matching the search criteria. |
| total | integer | No | This field is reserved for internal or future use. |
