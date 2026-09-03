---
title: bulkUpdateConversation
category: M2M_Public_API_Service
api_name: bulkUpdateConversation
method: POST
path: /bulk_update_conversation
---

**Category:** M2M_Public_API_Service
**API:** bulkUpdateConversation

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/bulk_update_conversation

## API Description
This method can be used to update the conversationStatus of up to 10 conversations. The conversationId , existing conversationType , and updated conversationStatus for each conversation to modify are required in the conversations array. Important! Though it cannot be updated, the conversationType field is required for each conversation being updated. If the updates were successful, the conversationId of each conversation will be returned with an associated updateStatus value of SUCCESSFUL .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversations | array<BulkConversation> | No | This array specifies the list of conversations to update and the updated conversationStatus for each. |
| conversations.conversationId | string | No | This field indicates the unique identifier of the conversation that is to be updated. Use the getConversations method to retrieve conversation ID values. |
| conversations.conversationStatus | string | No | This field indicates the status for which to update the associated conversation. Valid values: ACTIVE ARCHIVE DELETE READ UNREAD |
| conversations.conversationType | string | No | This field specifies the existing type of the conversation that is to be updated. Important! This value cannot be updated using this method, but is required for each conversation being updated. Valid values: FROM_MEMBERS FROM_EBAY |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| conversationsMetadata | ConversationsMetadata | No | This container returns metadata from the call, such as how many conversations were updated, how many succeeded, and how many failed. |
| conversationsMetadata.totalConversationsCount | integer | No | The total amount of conversations being updated. |
| conversationsMetadata.updateFailureCount | integer | No | The number of conversations in which the specified update failed. |
| conversationsMetadata.updateSuccessCount | integer | No | The number of conversations in which the specified update succeeded. |
| conversationsResponse | array<ConversationsResponse> | No | This array returns a list of each conversation specified in the request, and if the requested update was successful or failed. |
| conversationsResponse.conversationId | string | No | The unique identifier of the conversation. |
| conversationsResponse.updateStatus | string | No | The update status of the conversation, such as SUCCESS or FAILURE . |
