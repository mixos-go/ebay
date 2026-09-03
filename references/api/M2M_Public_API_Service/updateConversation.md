---
title: updateConversation
category: M2M_Public_API_Service
api_name: updateConversation
method: POST
path: /update_conversation
---

**Category:** M2M_Public_API_Service
**API:** updateConversation

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/update_conversation

## API Description
This method can be used to update the conversationStatus or the read status of a specified conversation. Note: Only one of these statuses can be updated at a time using this method. If both fields are included, only the read status of the specified conversation will be updated and the conversationStatus field will be ignored. The conversationId of the conversation to modify, as well as the existing conversationType of the specified conversation are required as part of the request payload. Important! Though it cannot be updated, the existing conversationType of the specified conversation to be updated is required in the request payload. If this value is not provided, an error will occur. To update a conversation's status (for example, updating an ACTIVE conversation to ARCHIVE ), include the conversationStatus field in the request with the updated value. To update a conversation's read status (for example, updating an UNREAD conversation to READ ), include the read boolean in the request with the updated value.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversationId | string | No | This field specifies the unique identifier of the conversation that is to be updated. Use the getConversations method to retrieve conversation ID values |
| conversationStatus | string | No | This field specifies the status for which to update the specified conversation. Valid values: ACTIVE ARCHIVE DELETE Note: This field should not be used in conjunction with the read field. If both fields are input in the request, only the read status will be updated for the specified conversation and |
| conversationType | string | No | This field specifies the existing type of the conversation being updated. Important! This value cannot be updated using this method, but is required as part of the request payload. Valid values: FROM_MEMBERS FROM_EBAY |
| read | boolean | No | This boolean specifies the read status for which to update the conversation. If set to true , the conversation will update to 'read', and if set to false , the conversation will update to 'unread'. Note: This field should not be used in conjunction with the conversationStatus field. If both fields a |

## Response
_No documented response fields._
