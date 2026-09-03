---
title: updateCustomPolicy
category: Account_v1_API
api_name: updateCustomPolicy
method: PUT
path: /custom_policy/{custom_policy_id}
---

**Category:** Account_v1_API
**API:** updateCustomPolicy

**Method:** PUT
**HTTP Path:** https://api.ebay.com{basePath}/custom_policy/{custom_policy_id}

## API Description
This method updates an existing custom policy specified by the custom_policy_id path parameter. Since this method overwrites the policy's name , label , and description fields, always include the complete and current text of all three policy fields in the request payload, even if they are not being updated. For example, the value for the label field is to be updated, but the name and description values will remain unchanged. The existing name and description values, as they are defined in the current policy, must also be passed in. A successful policy update call returns an HTTP status code of 204 No Content .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| custom_policy_id (path) | string | Yes | This path parameter is the unique identifier of the custom policy to update. Note: A list of custom policies defined for a seller's account that includes this ID can be retrieved by calling the getCustomPolicies method. |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| description | string | No | Contains the seller specified policy and policy terms. Note: Always supply this field. If this field is not specified, any previous value is removed. Call the getCustomPolicy method to return the present field value for this policy. Max length: 15,000 |
| label | string | No | Customer-facing label shown on View Item pages for items to which the policy applies. This seller-defined string is displayed as a system-generated hyperlink pointing to seller specified policy information. Note: Always supply this field. If this field is not specified, any previous value is removed |
| name | string | No | The seller-defined name for the custom policy. Names must be unique for policies assigned to the same seller and policy type. Note: This field is visible only to the seller. Note: Always supply this field. If this field is not specified, any previous value is removed. Call the getCustomPolicy method |

## Response
_No documented response fields._
