---
title: createCustomPolicy
category: Account_v1_API
api_name: createCustomPolicy
method: POST
path: /custom_policy/
---

**Category:** Account_v1_API
**API:** createCustomPolicy

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/custom_policy/

## API Description
This method creates a new custom policy that specifies the seller's terms for complying with local governmental regulations. Each Custom Policy targets a policyType . Multiple policies may be created as using the following custom policy types: PRODUCT_COMPLIANCE: Product Compliance policies disclose product information as required for regulatory compliance. Note: A maximum of 60 Product Compliance policies per seller may be created. TAKE_BACK: Takeback policies describe the seller's legal obligation to take back a previously purchased item when the buyer purchases a new one. Note: A maximum of 18 Takeback policies per seller may be created. A successful create policy call returns an HTTP status code of 201 Created with the system-generated policy ID included in the Location response header.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| description | string | No | Contains the seller's policy and policy terms. Max length: 15,000 |
| label | string | No | Customer-facing label shown on View Item pages for items to which the policy applies. This seller-defined string is displayed as a system-generated hyperlink pointing to the seller's policy information. Max length: 65 |
| name | string | No | The seller-defined name for the custom policy. Names must be unique for policies assigned to the same seller and policy type. Note: This field is visible only to the seller. Max length: 65 |
| policyType | string | No | Specifies the type of custom policy being created. Two Custom Policy types are supported: Product Compliance (PRODUCT_COMPLIANCE) Takeback (TAKE_BACK) For implementation help, refer to eBay API documentation |

## Response
_No documented response fields._
