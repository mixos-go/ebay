---
title: uploadVideo
category: Media_API
api_name: uploadVideo
method: POST
path: /video/{video_id}/upload
---

**Category:** Media_API
**API:** uploadVideo

**Method:** POST
**HTTP Path:** https://apim.ebay.com{basePath}/video/{video_id}/upload

## API Description
This method associates the specified file with the specified video ID and uploads the input file. After the file has been uploaded the processing of the file begins. Note: The size of the video to be uploaded must exactly match the size of the video's input stream that was set in the createVideo method. If the sizes do not match, the video will not upload successfully. When a video is successfully uploaded, it returns the HTTP Status Code 200 OK . The status flow is PENDING_UPLOAD > PROCESSING > LIVE , PROCESSING_FAILED , or BLOCKED . After a video upload is successfully completed, the status will show as PROCESSING until the video reaches one of the terminal states of LIVE , BLOCKED , or PROCESSING_FAILED . If the size information (in bytes) provided is incorrect, the API will throw an error. Tip: See Adding a video to your listing in the eBay Seller Center for details about video formatting requirements and restrictions, or visit the relevant eBay site help pages for the region in which the listings will be posted. To retrieve an uploaded video, use the getVideo method. Important! All POST methods in the Media API, including this method, are subject to short-duration rate limits at the user level: 50 requests per 5 seconds.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Length (header) | string | No | Use this header to specify the content length for the upload. Use Content-Range: bytes {1}-{2}/{3} and Content-Length:{4} headers. Note: This header is optional and is only required for resumable uploads (when an upload is interrupted and must be resumed from a certain point). |
| Content-Range (header) | string | No | Use this header to specify the content range for the upload. The Content-Range should be of the following bytes ((?:[0-9]+-[0-9]+)\|\\\\*)/([0-9]+\|\\\\*) pattern. Note: This header is optional and is only required for resumable uploads (when an upload is interrupted and must be resumed from a certain |
| Content-Type (header) | string | Yes | Use this header to specify the content type for the upload. The Content-Type should be set to application/octet-stream . |
| video_id (path) | string | Yes | The unique identifier of the video to be uploaded. |

## Response
_No documented response fields._
