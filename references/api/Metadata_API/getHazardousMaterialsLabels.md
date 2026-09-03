---
title: getHazardousMaterialsLabels
category: Metadata_API
api_name: getHazardousMaterialsLabels
method: GET
path: /marketplace/{marketplace_id}/get_hazardous_materials_labels
---

**Category:** Metadata_API
**API:** getHazardousMaterialsLabels

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_hazardous_materials_labels

## API Description
This method returns hazardous materials label information for the specified eBay marketplace. The information includes IDs, descriptions, and URLs (as applicable) for the available signal words, statements, and pictograms. The returned statements are localized for the default language of the marketplace. If a marketplace does not support hazardous materials label information, no response payload is returned, but only a 204 No content status code. This information is used by the seller to add hazardous materials label related information to their listings (see Specifying hazardous material related information ).

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which hazardous materials label information shall be retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| signalWords | array<SignalWord> | No | This array contains available hazardous materials signal words for the specified marketplace. |
| signalWords.signalWordId | string | No | The identifier of the signal word. For more information, see Signal word information . |
| signalWords.signalWordDescription | string | No | The description of the signal word localized to the default language of the marketplace. For more information, see Signal word information . |
| statements | array<HazardStatement> | No | This array contains available hazardous materials hazard statements for the specified marketplace. |
| statements.statementId | string | No | The identifier of the statement. For sample values, see Hazard statement sample values . |
| statements.statementDescription | string | No | The description of the statement localized to the default language of the marketplace. For sample values, see Hazard statement sample values . |
| pictograms | array<Pictogram> | No | This array contains available hazardous materials hazard pictograms for the specified marketplace. |
| pictograms.pictogramId | string | No | The identifier of the pictogram. For sample values, see Pictogram sample values . |
| pictograms.pictogramDescription | string | No | The description of the pictogram localized to the default language of the marketplace. For sample values, see Pictogram sample values . |
| pictograms.pictogramUrl | string | No | The URL of the pictogram. |
