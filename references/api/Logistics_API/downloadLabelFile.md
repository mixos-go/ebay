---
title: downloadLabelFile
category: Logistics_API
api_name: downloadLabelFile
method: GET
path: /shipment/{shipmentId}/download_label_file
---

**Category:** Logistics_API
**API:** downloadLabelFile

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipment/{shipmentId}/download_label_file

## API Description
This method returns the shipping label file that was generated for the shipmentId value specified in the request. Call createFromShippingQuote to generate a shipment ID. Note: The Logistics API only supports USPS shipping rates and labels. Use the Accept HTTP header to specify the format of the returned file. The default file format is a PDF file.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId (path) | string | Yes | This path parameter specifies the unique eBay-assigned identifier of the shipment associated with the shipping label you want to download. The shipmentId value is generated and returned by the createFromShippingQuote method. |
| Accept (header) | string | Yes | This header specifies the format of the returned file. For this method, the value of the header should be Accept: application/pdf . |

## Response
_No documented response fields._
