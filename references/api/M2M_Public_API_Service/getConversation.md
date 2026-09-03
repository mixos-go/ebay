---
title: getConversation
category: M2M_Public_API_Service
api_name: getConversation
method: GET
path: /conversation/{conversation_id}
---

**Category:** M2M_Public_API_Service
**API:** getConversation

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/conversation/{conversation_id}

## API Description
This method can be used to retrieve messages within a specific conversation. The conversation_id of the conversation for which to retrieve messages is required as path parameters, and the and conversation_type of the conversation is required as a query parameter.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversation_id (path) | string | Yes | This path parameters specifies the unique identifier of the conversation that is to be retrieved. Use the getConversations method to retrieve conversation ID values. |
| conversation_type (query) | string | Yes | This query parameter specifies the type of the conversation being retrieved. This parameter is always required when using the this method. Valid values: FROM_EBAY FROM_MEMBERS |
| limit (query) | string | No | The maximum number of entries that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. For example, if offset is set to 10 and limit is set to 10 , the call retrieves entries 11 through 20 from t |
| offset (query) | string | No | The number of reports to skip in the result set before returning the first entry in the paginated response. Use this parameter in conjunction with the limit parameter to control the pagination of the output. For example, if offset is set to 0 and limit is set to 10 , the first page of the response w |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversationStatus | string | No | The current status of the conversation, such as ACTIVE or ARCHIVE . |
| conversationTitle | string | No | The title of the conversation. |
| conversationType | string | No | The type of the conversation, such as FROM_EBAY or FROM_MEMBERS . |
| href | string | No | The URI to the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request. |
| messages | array<MessageDetail> | No | This array returns a list of messages from the specified conversation. |
| messages.createdDate | string | No | The date, in ISO 8601 format, the message was received. |
| messages.messageBody | string | No | The message text. |
| messages.messageId | string | No | The unique identifier of the message. |
| messages.messageMedia | array<MessageMedia> | No | This array returns a list, if applicable, of media attached to the message. |
| messages.messageMedia.mediaName | string | No | The name of the media attached to the message. |
| messages.messageMedia.mediaType | string | No | The type of media attached to the message. Valid values: IMAGE PDF DOC TXT |
| messages.messageMedia.mediaUrl | string | No | The URL of the self-hosted media attached to the message. URLs must use the "HTTPS" protocol. |
| messages.readStatus | boolean | No | This boolean indicates if the message has been viewed by the recipient. If this boolean is returned as true , the message has been read. If this boolean is returned as false , the message has not been read. |
| messages.recipientUsername | string | No | The eBay username of the message recipient. |
| messages.senderUsername | string | No | The eBay username of the message sender. |
| messages.subject | string | No | The subject line of the message. |
| next | string | No | The URI for the next page of results. This value is only returned if there is an additional page of results in the result set. |
| offset | integer | No | The value of the offset parameter submitted in the request. |
| prev | string | No | The URI for the previous page of results. This is only retuned if there is a previous page of results in the result set. |
| total | integer | No | The total number of entries returned in the result set. |
