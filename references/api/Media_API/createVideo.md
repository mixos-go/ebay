---
title: createVideo
category: Media_API
api_name: createVideo
method: POST
path: /video
---

**Category:** Media_API
**API:** createVideo

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/video

## API Description
This method creates a video resource. When using this method, specify the title , size , and classification of the video resource to be created. Description is an optional field for this method. Tip: See Adding a video to your listing in the eBay Seller Center for details about video formatting requirements and restrictions, or visit the relevant eBay site help pages for the region in which the listings will be posted. When a video resource is successfully created, the method returns the HTTP Status Code 201 Created. The method also returns the location response header containing the video ID , which you can use to retrieve the video. Note: There is no ability to edit metadata on videos at this time. There is also no method to delete videos. To upload a created video to a created video resource, use the uploadVideo method. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| classification | array<string> | No | The intended use for this video content. Currently, videos can only be added and associated with eBay listings, so the only supported value is ITEM . |
| description | string | No | The description of the video. |
| size | integer | No | The size, in bytes, of the video content. Max: 157,286,400 bytes |
| title | string | No | The title of the video. |

## Response
_No documented response fields._
