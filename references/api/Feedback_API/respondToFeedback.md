---
title: respondToFeedback
category: Feedback_API
api_name: respondToFeedback
method: POST
path: /respond_to_feedback
---

**Category:** Feedback_API
**API:** respondToFeedback

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/respond_to_feedback

## API Description
This method allows users to respond to feedback provided by the order partner for a specific line item in an order. For each order, the order partner is the other participant in the transaction, either the buyer or seller, depending on the eBay user associated with the user token. This method allows the user to provide additional context or address the order partner's feedback. Note: The feedback response must adhere to community guidelines and be relevant to the transaction. You can only use this method if feedback has been provided by the order partner and you have not yet responded to it. When responding to feedback, your feedback score is not affected when you respond to feedback. For additional information on leaving feedback, see the following: Leaving feedback for sellers Leaving feedback for buyers A successful call returns an HTTP status of 200 Success .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedbackId | string | No | Use this field to provide the unique identifier for the feedback being responded to, used to specify the feedback entry associated with the feedback response. This value can be returned using the getFeedback method ( feedbackId field). |
| recipientUserId | string | No | Use this field to provide the identifier of the user who provided the original feedback. This value can be returned using the getFeedback method ( userId field). Note: Both usernames and public user IDs will be accepted in this field. For more information, please refer to Data Handling Compliance . |
| responseText | string | No | Use this field to provide the text content of the response. This field is used to provide additional context or address the feedback given by the order partner. No HTML formatting or personal information (such as phone numbers) is permitted. Maximum length: 500 characters. |
| responseType | string | No | Set this enumerated value to describe the type of response being submitted (for example, a REPLY or a FOLLOW_UP ). For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
