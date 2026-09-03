---
title: getListingSet
category: Marketing_API
api_name: getListingSet
method: GET
path: /promotion/{promotion_id}/get_listing_set
---

**Category:** Marketing_API
**API:** getListingSet

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/promotion/{promotion_id}/get_listing_set

## API Description
Note: As of July 8th 2024, promotions are now being referred to as discounts on Seller Hub and eBay help pages. Sell Marketing API documentation has been updated to reflect this product name change, but note that no API interface changes have been made. This method returns the set of listings associated with the promotion_id specified in the path parameter. Call getPromotions to retrieve the IDs of a seller's discounts. The listing details are returned in a paginated set and you can control and results returned using the following query parameters: limit , offset , q , sort , and status . Maximum associated listings returned: 200 Default number of listings returned: 200

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | Specifies the maximum number of discounts returned on a page from the result set. Default: 200 Maximum: 200 |
| offset (query) | string | No | Specifies the number of discounts to skip in the result set before returning the first discount in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the first page of the  |
| promotion_id (path) | string | Yes | This path parameter takes a concatenation of the ID of the discount associated with the listing set plus the marketplace ID on which the discount is hosted. Concatenate the two values by separating them with an "at sign" ( @ ). The ID of the discount ( promotionId ) is a unique eBay-assigned value t |
| q (query) | string | No | Reserved for future use. |
| sort (query) | string | No | Specifies the order in which to sort the associated listings in the response. If you precede the supplied value with a dash, the response is sorted in reverse order. Example: &nbsp;&nbsp;&nbsp; sort=PRICE - Sorts the associated listings by their current price in ascending order &nbsp;&nbsp;&nbsp; so |
| status (query) | string | No | This query parameter applies only to markdown discounts. It filters the response based on the indicated status of the discount. Note: Currently, the only supported value for this parameter is MARKED_DOWN , which indicates active markdown discounts. For implementation help, refer to eBay API document |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| listings | array<ListingDetail> | No | An array of the listings associated with a discount. |
| listings.currentPrice | Amount | No | The container that returns the current price of the listing. |
| listings.currentPrice.currency | string | No | The base currency applied to the value field to establish a monetary amount. The currency is represented as a 3-letter ISO 4217 currency code. For example, the code for the Canadian Dollar is CAD For implementation help, refer to eBay API documentation |
| listings.currentPrice.value | string | No | The monetary amount in the specified currency . Required in the amount type. |
| listings.freeShipping | boolean | No | If set to true , the seller pays for the shipping (or that the item is marked for local pickup only) In this case, the listing does not have an associated shipping cost for the first listed domestic-shipping option (even if the first domestic-shipping option specifies a flat-rate or calculated shipp |
| listings.inventoryReferenceId | string | No | The seller's inventory reference ID for a listing. Also known as the "SKU" or "custom label," an inventory reference ID is either the ID of the listing or, if the listing has variations (such as a shirt that's available in multiple sizes and colors), the ID of the parent listing. |
| listings.inventoryReferenceType | string | No | Indicates the type of the inventoryReferenceId , which can be either a single-SKU or a multi-SKU listing ( INVENTORY_ITEM and INVENTORY_ITEM_GROUP , respectively). Note: This value is not currently returned in the response. |
| listings.listingCategoryId | string | No | The ID of the category that listing belongs to. The ID is a numeric and unique identifier for the category that is assigned by eBay. |
| listings.listingCondition | string | No | An eBay-assigned value that indicates condition of the associated item. For more information, see Item condition ID and name values . |
| listings.listingConditionId | string | No | The ID of the condition associated with the item. For more information, see Item condition ID and name values . Note: This value is not currently returned in the response. |
| listings.listingId | string | No | A unique eBay-assigned ID that is generated when the item is listed. |
| listings.listingPromotionStatuses | array<ItemMarkdownStatus> | No | A list of the status values assigned to the item and the date that each new status was assigned. |
| listings.listingPromotionStatuses.listingMarkdownStatus | string | No | Indicates the state assigned to the markdown discount using one of the status values. For implementation help, refer to eBay API documentation |
| listings.listingPromotionStatuses.statusChangedDate | string | No | Identifies the date the last time the state of the discount changed. Both both markdown and markup events can trigger a status change. |
| listings.listingPromotionStatuses.statusMessage | string | No | An eBay-assigned text string that describes the status of the discount. |
| listings.quantity | integer | No | The number of items being sold in the listing. |
| listings.storeCategoryId | string | No | Store CategoryId (if any) that to which the listing belongs. This field is blank if there is no seller Store category ID. |
| listings.title | string | No | The seller-defined title of the listing that a seller can use to identify the item. This label is not displayed in end-user flows. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length : 2048 |
| total | integer | No | The total number of items retrieved in the result set. If no items are found, this field is returned with a value of 0 . |
| warnings | array<Error> | No | A list of warnings that were generated by the request. Warning do not stop processing, but should be checked to ensure that the response contains the correct information. |
| warnings.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| warnings.domain | string | No | Name of the domain containing the service or application. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| warnings.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the entity that threw the error. |
| warnings.parameters.value | string | No | A description of the error. |
| warnings.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
