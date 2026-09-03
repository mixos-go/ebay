---
title: getProductSafetyLabels
category: Metadata_API
api_name: getProductSafetyLabels
method: GET
path: /marketplace/{marketplace_id}/get_product_safety_labels
---

**Category:** Metadata_API
**API:** getProductSafetyLabels

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_product_safety_labels

## API Description
This method returns product safety label information for the specified eBay marketplace. The information includes IDs, descriptions, and URLs (as applicable) for the available statements and pictograms. The returned statements are localized for the default language of the marketplace. If a marketplace does not support product safety label information, no response payload is returned, but only a 204 No content status code. This information is used by the seller to add product safety label related information to their listings. The getRegulatoryPolicies method can be used to see which categories recommend or require product safety labels.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information is retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. See the following note for exceptions. Note: This method is not supported in the EBAY_HK , EBAY_MY , EBAY_TW , or EBAY_PH marketp |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| pictograms | array<ProductSafetyLabelPictogram> | No | This array contains a list of pictograms of product safety labels for the specified marketplace. |
| pictograms.pictogramDescription | string | No | The description of the pictogram localized to the default language of the marketplace. |
| pictograms.pictogramId | string | No | The identifier of the pictogram. |
| pictograms.pictogramUrl | string | No | The URL of the pictogram. |
| statements | array<ProductSafetyLabelStatement> | No | This array contains available product safety labels statements for the specified marketplace. |
| statements.statementDescription | string | No | The description of the statement localized to the default language of the marketplace. |
| statements.statementId | string | No | The identifier of the statement. |
