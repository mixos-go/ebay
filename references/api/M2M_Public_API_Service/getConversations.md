---
title: getConversations
category: M2M_Public_API_Service
api_name: getConversations
method: GET
path: /conversation
---

**Category:** M2M_Public_API_Service
**API:** getConversations

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/conversation

## API Description
This method can be used to retrieve one or more conversations associated with a user. The conversation_type query parameter is required when using this method to specify if the retrieved conversations are from eBay or from members. The result set can also optionally be filtered by conversation status, reference, username, and/or time range. The limit and offset path parameters can be used to paginate the result set and control how many conversations are returned in the response.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversation_status (query) | string | No | This query parameter specifies the status of the conversations being retrieved. Only conversations in the specified status will be returned. Valid values: ACTIVE ARCHIVE DELETE READ UNREAD |
| conversation_type (query) | string | Yes | This query parameter specifies the type of the conversations being retrieved. Only conversations of the specified type will be returned. This parameter is always required when using this method. Valid values: FROM_EBAY FROM_MEMBERS |
| end_time (query) | string | No | This query parameter specifies the end time (in ISO 8601 format) for which to stop retrieving conversations. For example, if set to 2024-11-06T10:00:00.000Z , only messages sent before this time will be retrieved. Format: yyyy-MM-ddThh:mm.ss.sssZ Note: Currently, this parameter is only available if  |
| limit (query) | string | No | The maximum number of entries that can be returned on each page of the paginated response. Use this parameter in conjunction with the offset parameter to control the pagination of the output. For example, if offset is set to 10 and limit is set to 10 , the call retrieves entries 11 through 20 from t |
| offset (query) | string | No | The number of reports to skip in the result set before returning the first entry in the paginated response. Use this parameter in conjunction with the limit parameter to control the pagination of the output. For example, if offset is set to 0 and limit is set to 10 , the first page of the response w |
| other_party_username (query) | string | No | This query parameter specifies the user name (login name) of an eBay user for which to retrieve conversations. If this filter is used, only conversation(s) from the other eBay user specified through this parameter will be returned. |
| reference_id (query) | string | No | This query parameter specifies the unique identifier of the reference (specified by the corresponding reference_type value) associated with the conversation. Only conversations associated with the specified reference ID will be returned. For example, in the case of a LISTING reference, this value wi |
| reference_type (query) | string | No | This query parameter specifies the type of reference associated with a conversation. The reference type is used to specify what the conversation is in reference to. For example, a value of LISTING specifies that the conversation is associated with a specific listing. The item ID associated with this |
| start_time (query) | string | No | This query parameter specifies the start time (in ISO 8601 format) for which to start retrieving conversations. For example, if set to 2024-11-06T10:00:00.000Z , only messages sent after this time will be retrieved. Format: yyyy-MM-ddThh:mm.ss.sssZ Note: Currently, this parameter is only available i |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversations | array<ConversationDetail> | No | This array returns the conversations that match the filter criteria. Each conversation is returned with information such as its ID, status, title, type, and creation date, as well as the latest message in the conversation. |
| conversations.conversationId | string | No | The unique identifier of the conversation. |
| conversations.conversationStatus | string | No | This value indicates the current status of the conversation, such as ACTIVE or ARCHIVE . |
| conversations.conversationTitle | string | No | The title of the conversation. |
| conversations.conversationType | string | No | This value indicates the type of the conversation, such as FROM_EBAY or FROM_MEMBERS . |
| conversations.createdDate | string | No | This value indicates the date, in ISO 8601 format, the conversation was created. |
| conversations.latestMessage | MessageDetail | No | This container returns the latest message in the conversation and its details. |
| conversations.latestMessage.createdDate | string | No | The date, in ISO 8601 format, the message was received. |
| conversations.latestMessage.messageBody | string | No | The message text. |
| conversations.latestMessage.messageId | string | No | The unique identifier of the message. |
| conversations.latestMessage.messageMedia | array<MessageMedia> | No | This array returns a list, if applicable, of media attached to the message. |
| conversations.latestMessage.messageMedia.mediaName | string | No | The name of the media attached to the message. |
| conversations.latestMessage.messageMedia.mediaType | string | No | The type of media attached to the message. Valid values: IMAGE PDF DOC TXT |
| conversations.latestMessage.messageMedia.mediaUrl | string | No | The URL of the self-hosted media attached to the message. URLs must use the "HTTPS" protocol. |
| conversations.latestMessage.readStatus | boolean | No | This boolean indicates if the message has been viewed by the recipient. If this boolean is returned as true , the message has been read. If this boolean is returned as false , the message has not been read. |
| conversations.latestMessage.recipientUsername | string | No | The eBay username of the message recipient. |
| conversations.latestMessage.senderUsername | string | No | The eBay username of the message sender. |
| conversations.latestMessage.subject | string | No | The subject line of the message. |
| conversations.referenceId | string | No | This value indicates the reference ID associated with the corresponding referenceType value. In the case of a LISTING referenceType , this value will be the item ID value of the associated listing. |
| conversations.referenceType | string | No | This value indicates the reference type, if applicable, associated with the conversation. The reference type is used to specify what the conversation is in reference to. For example, a value of LISTING specifies that the conversation is associated with a specific listing. The item ID associated with |
| conversations.unreadCount | integer | No | This value indicates the amount of unread messages in the conversation. |
| href | string | No | The URI to the current page of results. |
| limit | integer | No | The value of the limit parameter submitted in the request. |
| next | string | No | The URI for the next page of results. This value is returned if there is an additional page of results in the result set. |
| offset | integer | No | The value of the offset parameter submitted in the request. |
| prev | string | No | The URI for the previous page of results. This is retuned if there is a previous page of results in the result set. |
| total | integer | No | The total number of entries returned in the result set. |
