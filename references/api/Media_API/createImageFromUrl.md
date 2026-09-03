---
title: createImageFromUrl
category: Media_API
api_name: createImageFromUrl
method: POST
path: /image/create_image_from_url
---

**Category:** Media_API
**API:** createImageFromUrl

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/image/create_image_from_url

## API Description
This method uploads a picture to eBay Picture Services (EPS) from the specified URL. Specify the location of the picture on an external web server through the imageUrl field. All images must comply with eBay’s picture requirements, such as dimension and file size restrictions. For more information, see Picture policy . The image formats supported are JPG , GIF , PNG , BMP , TIFF , AVIF , HEIC , and WEBP . In addition, the provided URL must be secured using HTTPS (HTTP is not permitted). For more information, see Image requirements . Note: Animated GIF, and multi-page PNG/TIFF files, are not supported. Any animation effect of supported formats will be lost upon upload. When an EPS image is successfully created, the method returns the HTTP Status Code 201 Created . The method also returns the getImage URI in the Location response header. Important! Make sure to capture the image ID URI returned in the response location header provided in the following format: https://apim.ebay.com/commerce/media/v1_beta/image/ {image_id} You can capture the entire URI, or just save the {image_id} only. Pass the {image_id} as a path parameter in the getImage method to return the value needed to associate an image to a listing using the Trading and Inventory APIs. See Managing images for additional details. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| imageUrl | string | No | The image URL of the self-hosted picture to upload to eBay Picture Services (EPS). In addition to the picture requirements in Picture policy , the provided URL must be secured using HTTPS (HTTP is not permitted). For more information, see Image requirements . |

## Response
_No documented response fields._
