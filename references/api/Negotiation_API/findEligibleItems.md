---
title: findEligibleItems
category: Negotiation_API
api_name: findEligibleItems
method: GET
path: /find_eligible_items
---

**Category:** Negotiation_API
**API:** findEligibleItems

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/find_eligible_items

## API Description
This method evaluates a seller's current listings and returns the set of IDs that are eligible for a seller-initiated discount offer to a buyer. A listing ID is returned only when one or more buyers have shown an "interest" in the listing. If any buyers have shown interest in a listing, the seller can initiate a "negotiation" with them by calling sendOfferToInterestedBuyers , which sends all interested buyers a message that offers the listing at a discount. For details about how to create seller offers to buyers, see Sending offers to buyers .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | This query parameter specifies the maximum number of items to return from the result set on a page in the paginated response. Minimum: 1 Maximum: 200 Default: 10 |
| offset (query) | string | No | This query parameter specifies the number of results to skip in the result set before returning the first result in the paginated response. Combine offset with the limit query parameter to control the items returned in the response. For example, if you supply an offset of 0 and a limit of 10 , the f |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The eBay marketplace on which you want to search for eligible listings. For a complete list of supported marketplaces, see Negotiation API requirements and restrictions . |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| eligibleItems | array<EligibleItem> | No | A list of items that are eligible for a seller-initiated offer to a buyer. Each element in the list contains the listing ID or the SKU value--> of a listed item. These IDs represent the listings for which buyers have shown an interest. |
| eligibleItems.listingId | string | No | The unique eBay-assigned ID for an eBay listing. A listingId is assigned by eBay when a seller creates a listing with the Trading API. |
| href | string | No | The URI of the current page of results from the result set. |
| limit | integer | No | The number of items returned on a single page from the result set. This value can be set in the request with the limit query parameter. |
| next | string | No | The URI for the following page of results. This value is returned only if there is an additional page of results to display from the result set. Max length : 2048 |
| offset | integer | No | The number of results skipped in the result set before listing the first returned result. This value can be set in the request with the offset query parameter. Note: The items in a paginated result set use a zero-based list where the first item in the list has an offset of 0 . |
| prev | string | No | The URI for the preceding page of results. This value is returned only if there is a previous page of results to display from the result set. Max length : 2048 |
| total | integer | No | The total number of items retrieved in the result set. If no items match the search criteria, the server returns the HTTP status code 204 No Content . |
