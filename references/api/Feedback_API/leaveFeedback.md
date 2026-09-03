---
title: leaveFeedback
category: Feedback_API
api_name: leaveFeedback
method: POST
path: /feedback
---

**Category:** Feedback_API
**API:** leaveFeedback

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/feedback

## API Description
This method creates and submits feedback to the user's order partner for a line item in the order. For each order, the order partner is the other participant in the transaction, either the buyer or seller, depending on the eBay user associated with the user token. This method allows users to provide detailed information about the transaction, including the feedback rating, comments, and seller delivery. You can also add images to your feedback. Note: A seller can only provide a comment for a buyer, but a buyer can provide a comment plus provides ratings on a number of metrics for a seller. Note: The feedback must adhere to community guidelines and be relevant to the transaction. When leaving feedback, keep the following in mind: Your feedback score is not affected when you leave feedback Feedback can only be revised once after it is submitted For additional information on leaving feedback, see the following: Leaving feedback for sellers Leaving feedback for buyers A successful call to this method returns a feedback ID, which is a unique identifier for the newly created feedback and allows for reference and tracking.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| commentText | string | No | Use this field to provide the feedback left by the user, describing their experience with the line item of the transaction. No HTML formatting or personal information (such as phone numbers) is permitted. Maximum length: 500 characters |
| commentType | string | No | Set this enumerated value to indicate the overall rating of the transaction: POSITIVE , NEUTRAL , or NEGATIVE . Note: Sellers can only provide positive feedback. For implementation help, refer to eBay API documentation |
| images | array<Image> | No | Use this array to optionally list up to 5 images attached to the feedback. |
| images.url | string | No | This field provides the URL of an attached image and is included in the response whenever an image is attached. |
| listingId | string | No | Use this field to provide the listing ID related to the transaction. |
| orderLineItemId | string | No | Use this field to provide the unique identifier of the line item for this feedback. |
| sellerRatings | array<SellerRating> | No | Use this array to list ratings for specific aspects of the seller's performance. |
| sellerRatings.key | string | No | The enumerated value of the category being rated, such as delivery timeliness ( ON_TIME_DELIVERY ). For implementation help, refer to eBay API documentation |
| sellerRatings.value | string | No | The value assigned for the selected category. Use a value of 1 through 5 , with the 1 being the lowest rating and 5 being the highest. |
| transactionId | string | No | Use this field to provide the unique identifier of the transaction for this feedback. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedbackId | string | No | The unique ID assigned to the submitted feedback. |
