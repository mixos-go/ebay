---
title: sendMessage
category: M2M_Public_API_Service
api_name: sendMessage
method: POST
path: /send_message
---

**Category:** M2M_Public_API_Service
**API:** sendMessage

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/send_message

## API Description
This method can be used to start a conversation with another user or send a message in an existing conversation with another user based on the information provided in the request. To send a message, one of the conversationId or otherPartyUsername request fields are required. The conversationId must be used when sending a message in an existing conversation and specifies the conversation for which to send the message. For a new conversation, the otherPartyUsername field must be used to send the message to a specific user. In addition, the messageText field is required as it contains the body text of the message. Optionally, media (such as images or documents) can be attached to the message using the messageMedia container. The reference container can also be used to associate a message with a listing.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversationId | string | No | This field specifies the unique identifier of the conversation in which to send the message. Use the getConversations method to retrieve conversation ID values. This field is required if sending a message in an existing conversation. |
| emailCopyToSender | boolean | No | This boolean indicates whether a copy of the message should be emailed to the sender. If this boolean is input as true , a copy of the message will be emailed to the sender. |
| messageMedia | array<MessageMedia> | No | This array lists the individual forms of media, if any, to be attached to the message. Up to five individual forms of media may be be sent per message. If more than five are specified in this array, an error will occur and the call will fail. |
| messageMedia.mediaName | string | No | The name of the media attached to the message. |
| messageMedia.mediaType | string | No | The type of media attached to the message. Valid values: IMAGE PDF DOC TXT |
| messageMedia.mediaUrl | string | No | The URL of the self-hosted media attached to the message. URLs must use the "HTTPS" protocol. |
| messageText | string | No | The text of the message. Max length: 2000 characters |
| otherPartyUsername | string | No | This field specifies the eBay username of the entity for which to send the message. This field is required if starting a new conversation with another eBay user. |
| reference | Reference | No | This container should be used if the new or existing conversation is related to a specific eBay listing. For example, a referenceType of LISTING and an associated referenceId will specify the item ID value of the listing associated with the message. |
| reference.referenceId | string | No | This value indicates the reference ID associated with the corresponding referenceType value. For example, in the case of a LISTING reference type, this value will be the item ID value of the listing. |
| reference.referenceType | string | No | This value indicates the reference type to associate with the conversation. The reference type is used to specify what the conversation is in reference to. For example, a value of LISTING specifies that the conversation is associated with a specific listing. The item ID associated with this listing  |

## Response
_No documented response fields._
