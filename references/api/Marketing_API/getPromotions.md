---
title: getPromotions
category: Marketing_API
api_name: getPromotions
method: GET
path: /promotion
---

**Category:** Marketing_API
**API:** getPromotions

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/promotion

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method returns a list of a seller's undeleted discounts. The call returns up to 200 currently-available discounts on the specified marketplace. While the response body does not include the discount's discountRules or inventoryCriterion containers, it does include the promotionHref (which you can use to retrieve the complete details of the discount). Use query parameters to sort and filter the results by the number of discounts to return, the discount state or type, and the eBay marketplace. You can also supply keywords to limit the response to the discounts that contain that keywords in the title of the discount. Maximum returned: 200

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | Specifies the maximum number of discounts returned on a page from the result set. Default: 200 Maximum: 200 |
| marketplace_id (query) | string | Yes | This parameter specifies eBay marketplace ID of the site where the discount is hosted. See MarketplaceIdEnum for supported Marketplace ID values. |
| offset (query) | string | No | Specifies the number of discounts to skip in the result set before returning the first discount in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the  |
| promotion_status (query) | string | No | This parameter specifies the discount state by which you want to filter the results. The response contains only those discounts that match the state you specify. See PromotionStatusEnum for supported values. Maximum number of input values: 1 |
| promotion_type (query) | string | No | This parameter specifies the campaign discounts type by which you want to filter the results. See PromotionTypeEnum for supported values. |
| q (query) | string | No | A string consisting of one or more keywords . eBay filters the response by returning only the discounts that contain the supplied keywords in the title. Example: "iPhone" or "Harry Potter." Commas that separate keywords are ignored. For example, a keyword string of "iPhone, iPad" equals "iPhone iPad |
| sort (query) | string | No | Specifies the order for how to sort the response. If you precede the supplied value with a dash, the response is sorted in reverse order. Example: &nbsp;&nbsp;&nbsp; sort=END_DATE &nbsp; Sorts the discounts in the response by their end dates in ascending order &nbsp;&nbsp;&nbsp; sort=-PROMOTION_NAME |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length : 2048 |
| promotions | array<PromotionDetail> | No | A list containing the details of each returned discount. This includes all the information about the discounts except for the listings that are discounted. |
| promotions.couponCode | string | No | A unique code that buyers can use during checkout to receive a discount. The code must be unique across eBay. |
| promotions.description | string | No | This is the seller-defined "tag line" for the offer, such as "Save on designer shoes." Tag lines appear under the "offer-type text" that is generated for a discount and displayed under the offer tile that is shown on the seller's All Offers page and on the discount's event page. Note: Offer-type tex |
| promotions.endDate | string | No | The date and time the discount ends in UTC format ( yyyy-MM-ddThh:mm:ssZ ). For display purposes, convert this time into the local time of the seller. |
| promotions.marketplaceId | string | No | The eBay marketplace ID of the site where the discount is hosted. Threshold discounts are supported on a select set of marketplaces while markdown discounts are supported on all eBay marketplaces. Valid values for threshold discounts are as follows: EBAY_AU = Australia EBAY_DE = Germany EBAY_ES = Sp |
| promotions.name | string | No | The seller-defined name or "title" of the discount, such as "Buy 1 Get 1", that the seller can use to identify a discount. This label is not displayed in end-user flows. Maximum length: 90 |
| promotions.priority | string | No | Applicable for only ORDER_DISCOUNT discount, this field indicates the precedence of the discount, which is used to determine the position of a discount on the seller's All Offers page. If an item is associated with multiple discounts, the discount with the higher priority takes precedence. For imple |
| promotions.promotionHref | string | No | The URI of the discount details. |
| promotions.promotionId | string | No | A unique eBay-assigned ID for the discount that's generated when the discount is created. |
| promotions.promotionImageUrl | string | No | Required for CODED_COUPON, MARKDOWN_SALE, and ORDER_DISCOUNT discount, and not applicable for VOLUME_DISCOUNT discounts, this field is a URL that points to an image for the discount. This image is displayed on the seller's All Offers page. The URL must point to either JPEG or PNG image and it must b |
| promotions.promotionStatus | string | No | The current status of the discount. When creating a new discount, you must set this value to either DRAFT or SCHEDULED . For implementation help, refer to eBay API documentation |
| promotions.promotionType | string | No | Indicates type of the discount, either CODED_COUPON , MARKDOWN_SALE , ORDER_DISCOUNT , or VOLUME_DISCOUNT . For implementation help, refer to eBay API documentation |
| promotions.startDate | string | No | The date and time the discount starts in UTC format ( yyyy-MM-ddThh:mm:ssZ ). For display purposes, convert this time into the local time of the seller. |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0 . |
