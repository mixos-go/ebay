---
title: getItemsAwaitingFeedback
category: Feedback_API
api_name: getItemsAwaitingFeedback
method: GET
path: /awaiting_feedback
---

**Category:** Feedback_API
**API:** getItemsAwaitingFeedback

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/awaiting_feedback

## API Description
This method retrieves line items awaiting feedback from the user's order partner. You can refine the results using optional filter query parameters, such as item ID, user name, or user role in the transaction. Sorting and pagination features help organize and navigate returned items efficiently. For sellers, only sold items that have not yet received feedback are included. For buyers, only purchased items for which feedback is still pending are included. If the user is both a buyer and a seller, this API returns items awaiting feedback for transactions where the user acted as either. Applying filters can limit results to either buyer-only or seller-only transactions. The response provides an overview of feedback yet to be left for completed transactions (as filtered), with counts for both the buyer and seller roles. It includes an array of line items, each containing the listing ID, title, price (with currency and value). For each line item, the response offers feedback templates specifying which ratings are available. Note: Detailed seller ratings are for sellers only, and are created from buyer feedback.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | Use this parameter to limit the response based on the specified filter parameters. Supported filter parameters include: listingId : Filter results by the specific listing ID receiverName : Filter results by the user's order partner name involved in the transaction userRole : Use this filter to only  |
| limit (query) | string | No | This parameter sets the maximum number of line items to return per page of data. Use this parameter in conjunction with the offset parameter to control the pagination of the output. For example, with offset set to 20 and limit set to 10 , the call retrieves entries 21 through 30 from the result set. |
| offset (query) | string | No | Use this parameter to specify the number of items to skip in the result set. This is used with the limit field to control the pagination of the output. For example: If offset is 0 and limit is 10 , the method will retrieve items 1-10 from the list of line items returned If offset is 10 and limit is  |
| sort (query) | string | No | Use this parameter to configure the order of the returned listings. The time is based on when the buyer paid for the line item. Acceptable values: END_TIME_ASC: Sorts listings by end time from oldest to newest END_TIME_DESC: Sorts listings by end time from newest to oldest (default) If this paramete |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| itemsAwaitingFeedbackCount | ItemsAwaitingFeedbackCount | No | This container returns the number of line items awaiting feedback. The asSeller and asBuyer fields return the total count of items awaiting feedback as seller and buyer and are not affected by the userRole filter. |
| itemsAwaitingFeedbackCount.asBuyer | integer | No | The number of line items for which feedback is pending from the user in the buyer role. |
| itemsAwaitingFeedbackCount.asSeller | integer | No | The number of line items for which feedback is pending from the user in the seller role. |
| lineItems | array<AwaitingFeedback> | No | This array contains the details for each line item awaiting feedback. An empty array is returned if no line items are awaiting feedback or that match the filter criteria. |
| lineItems.listingId | string | No | This is the unique identifier for the listing associated with the line item. It is used to reference the specific listing for which feedback is being awaited. |
| lineItems.listingPrice | ListingPrice | No | This container shows the sales price of the listing. |
| lineItems.listingPrice.currency | string | No | This field provides the three-letter ISO 4217 code that represents the currency of the amount in the value field. Both the value and currency fields are always returned when expressing prices. |
| lineItems.listingPrice.value | number | No | This field contains the numerical value of the listing price in the currency specified in the currency field. Both the value and currency fields are always returned when expressing prices. |
| lineItems.listingTitle | string | No | The title of the listing. |
| lineItems.orderLineItemId | string | No | The unique identifier for the eBay order line item associated with the listing. It is used to pinpoint the exact line item for which feedback is being awaited. |
| lineItems.ratingTemplates | array<FeedbackRatingTemplateType> | No | This array contains a list of available values for use in a particular rating, and whether the value is enabled. This is dependent on what seller ratings the buyer's order partner qualifies. Note: Rating templates should only be returned to the user in their role as a buyer; only sellers have Detail |
| lineItems.ratingTemplates.acceptableValues | array<FeedbackRatingAcceptableValue> | No | This array contains a list of available values for use in a particular rating, and whether the value is enabled. Provided if ratingValueType is RANGE or PREDEFINED . The following is an example of a predefined list: [ { "value": "POSITIVE", "valueLabel": "Positive", "enabled": true }, { "value": "NE |
| lineItems.ratingTemplates.acceptableValues.enabled | boolean | No | If true , this boolean indicates that this value is enabled and selectable. |
| lineItems.ratingTemplates.acceptableValues.value | string | No | The value that can be selected for feedback. For most ratingType values, this is 1 through 5 , with 1 representing the lowest rating and 5 representing the highest rating. For ratingType of OVERALL_EXPERIENCE , this can be POSITIVE , NEGATIVE , and NEUTRAL . These are the same values as used with th |
| lineItems.ratingTemplates.acceptableValues.valueLabel | string | No | This field provides information about the corresponding value . |
| lineItems.ratingTemplates.defaultValue | string | No | The default value preselected for the rating, if set. |
| lineItems.ratingTemplates.earlyFeedbackMessage | string | No | For eligible sellers, a message may be shown requiring a wait period before you can leave neutral or negative feedback. |
| lineItems.ratingTemplates.enabled | boolean | No | If returned as true , this boolean indicates that the corresponding feedback rating template is enabled for the user to provide feedback for this line item. This value will generally be true when the user role is a buyer, but false when the user role is a seller because buyers do not have Detailed S |
| lineItems.ratingTemplates.maximumCharactersAllowed | integer | No | The maximum number of characters allowed to be used for a rating that uses free text. It is only applicable for a rating whose ratingValueType is FREETEXT . Maximum: 500 |
| lineItems.ratingTemplates.multiValueRating | boolean | No | If returned as true , multiple values can be specified for the rating. |
| lineItems.ratingTemplates.ratingKey | string | No | This enumerated value indicates the type of rating that is tracked for the seller. All of the metadata returned under each node for the ratingTemplates array will apply to this rating type. For example, the value OVERALL_EXPERIENCE indicates the rating is for the overall transaction experience. For  |
| lineItems.ratingTemplates.ratingLabel | string | No | This field provides more details about and/or provides guidance on the corresponding rating type. For example, the rating label of Rate this transaction describes the feedback for the user to enter for an OVERALL_EXPERIENCE ratingKey . |
| lineItems.ratingTemplates.ratingValueType | string | No | This enumerated value indicates the type of data used to provide the specific feedback rating. If set to PREDEFINED or RANGE , is returned here, more information on the supported values will be returned under the acceptableValues array. If FREETEXT is returned here, the maximum number of characters  |
| lineItems.ratingTemplates.required | boolean | No | If returned as true , this rating type is required when leaving feedback. |
| lineItems.transactionId | string | No | The unique identifier of the sales transaction. |
| pagination | Pagination | No | This container provides pagination information for the returned line items awaiting feedback (as filtered). |
| pagination.count | integer | No | This value indicates the number of feedback entries on the current response page. |
| pagination.limit | integer | No | The value of the limit parameter submitted in the request. This is the maximum number of line items, as filtered, awaiting feedback to return per page from the result set. This field indicates the number of line items returned per page of data. Note: If this is the last or only page of the result se |
| pagination.next | string | No | The relative URI for the next page of results starting with the resource name. This URI is returned if there is an additional page of results in the result set. |
| pagination.offset | integer | No | The value of the offset parameter submitted in the request. This field indicates how many results were skipped in the response. If an offset parameter was not included in the request, this value will default to 0 , returning the first page of results. Default: 0 |
| pagination.prev | string | No | The relative URI for the previous page of results starting with the resource name. This URI is returned if there is a previous page of results in the result set. |
| pagination.total | integer | No | The total number of line items available that match the filter criteria. Note: If the total value exceeds the limit value, there are multiple pages of results. |
