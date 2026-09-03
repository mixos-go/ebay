---
title: getProduct
category: Catalog_API
api_name: getProduct
method: GET
path: /product/{epid}
---

**Category:** Catalog_API
**API:** getProduct

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/product/{epid}

## API Description
This method retrieves details of the catalog product identified by the eBay product identifier (ePID) specified in the request. These details include the product's title and description, aspects and their values, associated images, applicable category IDs, and any recognized identifiers that apply to the product. For a new listing, you can use the search method to identify candidate products on which to base the listing, then use the getProduct method to present the full details of those candidate products to the seller to make a a final selection.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| X-EBAY-C-MARKETPLACE-ID (header) | string | No | This method also uses the X-EBAY-C-MARKETPLACE-ID header to identify the seller's eBay marketplace. It is required for all supported marketplaces , except EBAY_US, which is the default. |
| epid (path) | string | Yes | The eBay product identifier (ePID) of the product being requested. This value can be discovered by issuing the search method and examining the value of the productSummaries.epid field for the desired returned product summary. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| additionalImages | array<Image> | No | Contains information about additional images associated with this product. For the primary image, see the image container. |
| additionalImages.height | integer | No | The height of the image in pixels. |
| additionalImages.imageUrl | string | No | The eBay Picture Services (EPS) URL of the image. |
| additionalImages.width | integer | No | The width of the image in pixels. |
| aspects | array<Aspect> | No | Contains an array of the category aspects and their values that are associated with this product. |
| aspects.localizedName | string | No | The localized name of this category aspect. |
| aspects.localizedValues | array<string> | No | A list of the localized values of this category aspect. |
| brand | string | No | The manufacturer's brand name for this product. |
| compatibilityCount | integer | No | The number of distinct motor vehicles that are compatible with the product. This field is only applicable for and will only be returned for Parts & Accessory products on the eBay US Motors marketplace. |
| description | string | No | The rich description of this product, which might contain HTML. |
| ean | array<string> | No | A list of all European Article Numbers (EANs) that identify this product. |
| epid | string | No | The eBay product ID of this product. |
| gtin | array<string> | No | A list of all GTINs that identify this product. Currently this can include EAN, ISBN, and UPC identifier types. |
| image | Image | No | Contains information about the primary image of this product. For more images of this product, see the additionalImages container. |
| image.height | integer | No | The height of the image in pixels. |
| image.imageUrl | string | No | The eBay Picture Services (EPS) URL of the image. |
| image.width | integer | No | The width of the image in pixels. |
| isbn | array<string> | No | A list of all International Standard Book Numbers (ISBNs) that identify this product. |
| mpn | array<string> | No | A list of all MPN values that the manufacturer uses to identify this product. |
| otherApplicableCategoryIds | array<string> | No | A list of category IDs (other than the value of primaryCategoryId ) for all the leaf categories to which this product might belong. |
| primaryCategoryId | string | No | The identifier of the leaf category that eBay recommends using to list this product, based on previous listings of similar products. Products in the eBay catalog are not automatically associated with any particular category, but using an inappropriate category can make it difficult for prospective b |
| productWebUrl | string | No | The URL for this product's eBay product page. |
| title | string | No | The title of this product on eBay. |
| upc | array<string> | No | A list of Universal Product Codes (UPCs) that identify this product. |
| version | string | No | The current version number of this product record in the catalog. |
