---
title: translate
category: Translation_API
api_name: translate
method: POST
path: /translate
---

**Category:** Translation_API
**API:** translate

**Method:** POST
**HTTP Path:** https://api.ebay.com{basePath}/translate

## API Description
This method translates listing title and listing description text from one language into another. For a full list of supported language translations, see the table .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| from | string | No | The language of the input text to be translated. Not all LanguageEnum values are supported in this field. For a full list of supported language pairings, see the Supported languages table . For implementation help, refer to eBay API documentation |
| text | array<string> | No | The input text to translate. The maximum number of characters permitted is determined by the translationContext value: ITEM_TITLE : 1000 characters maximum ITEM_DESCRIPTION : 20,000 characters maximum. Note: When translating ITEM_DESCRIPTION text, HTML/CSS markup and links can be included and will n |
| to | string | No | The target language for the translation of the input text. Not all LanguageEnum values are supported in this field. For a full list of supported language pairings, see the Supported languages table . For implementation help, refer to eBay API documentation |
| translationContext | string | No | Input the listing entity to be translated. Valid Values: ITEM_TITLE and ITEM_DESCRIPTION For implementation help, refer to eBay API documentation |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| from | string | No | The enumeration value indicates the language of the input text. For implementation help, refer to eBay API documentation |
| to | string | No | The enumeration value indicates the language of the translated text. For implementation help, refer to eBay API documentation |
| translations | array<Translation> | No | An array showing the input and translated text. Only one input string can be translated at this time. Support for multiple continuous text strings is expected in the future. |
| translations.originalText | string | No | The original text, in the language specified in the from field, that was input into the text field in the request. |
| translations.translatedText | string | No | The translation of the original text into the language specified in the to field. |
