---
title: getImage
category: Media_API
api_name: getImage
method: GET
path: /image/{image_id}
---

**Category:** Media_API
**API:** getImage

**Method:** GET
**HTTP Path:** https://apim.ebay.com{basePath}/image/{image_id}

## API Description
This method retrieves an EPS image URL and its expiration details for the unique identifier specified in the path parameter image_id . Use the retrieved EPS image URL to add the image to a listing through the Inventory API or the Trading API . See Managing images for additional details. Note: If a user inputs a valid image_id as a path parameter but the EPS image associated with that ID has expired, the call will fail and a 404 Not Found status code will be returned.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| image_id (path) | string | Yes | This path parameter is the unique identifier of a created image. Use the value returned in the location header of the method used to create the image ( createImageFromFile or createImageFromUrl , as applicable). |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| expirationDate | string | No | The date and time when an unused EPS image will expire and be removed from the EPS server, in Coordinated Universal Time (UTC). As long as an EPS image is being used in an active listing, that image will remain on the EPS server and be accessible. |
| imageUrl | string | No | The EPS URL to access the uploaded image. This URL will be used in listing calls to add the image to a listing. |
| maxDimensionImageUrl | string | No | The EPS URL to access the maximum dimension version of the uploaded image. |
