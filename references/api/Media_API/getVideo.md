---
title: getVideo
category: Media_API
api_name: getVideo
method: GET
path: /video/{video_id}
---

**Category:** Media_API
**API:** getVideo

**Method:** GET
**HTTP Path:** https://apim.ebay.com{basePath}/video/{video_id}

## API Description
This method retrieves a video's metadata and content given a specified video ID . The method returns the title , size , classification , description , video ID , playList , status , status message (if any), expiration date , and thumbnail image of the retrieved video. The video's title , size , classification , and description are set using the createVideo method. The video's playList contains two URLs that link to instances of the streaming video based on the supported protocol. The status field contains the current status of the video. After a video upload is successfully completed, the video's status will show as PROCESSING until the video reaches one of the terminal states of LIVE , BLOCKED or PROCESSING_FAILED . If a video's processing fails, it could be because the file is corrupted, is too large, or its size doesn't match what was provided in the metadata. Refer to the error messages to determine the cause of the video's failure to upload. The status message will indicate why a video was blocked from uploading. If a video is not being used on an active listing, its expiration date is automatically set to 30 days after the video's initial upload. The video's thumbnail image is automatically generated when the video is created.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| video_id (path) | string | Yes | The unique identifier of the video to be retrieved. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| classification | array<string> | No | The intended use for this video content. Currently, videos can only be added and associated with eBay listings, so the only supported value is ITEM . |
| description | string | No | The description of the video. The video description is an optional field that can be set using the createVideo method. |
| expirationDate | string | No | The date and time when an unused video will expire and be removed from the eBay Video Services server, in Coordinated Universal Time (UTC). As long as a video is being used in an active listing, that video will remain on the server and be accessible. If a video is not being used on an active listing |
| moderation | Moderation | No | The video moderation information that is returned if a video is blocked by moderators. Tip: See Video moderation and restrictions in the eBay Seller Center for details about video moderation. If the video status is BLOCKED , ensure that the video complies with eBay's video formatting and content gui |
| moderation.rejectReasons | array<string> | No | The reason(s) why the specified video was blocked by moderators. |
| playLists | array<Play> | No | The playlist created for the uploaded video, which provides the streaming video URLs to play the video. The supported streaming video protocols are DASH (Dynamic Adaptive Streaming over HTTP) and HLS (HTTP Live Streaming). The playlist will only be generated if a video is successfully uploaded with  |
| playLists.playUrl | string | No | The playable URL for this video. |
| playLists.protocol | string | No | The protocol for the video playlist. Supported protocols are DASH (Dynamic Adaptive Streaming over HTTP) and HLS (HTTP Live Streaming). For implementation help, refer to eBay API documentation |
| size | integer | No | The size, in bytes, of the video content. |
| status | string | No | The status of the current video resource. For implementation help, refer to eBay API documentation |
| statusMessage | string | No | The statusMessage field contains additional information on the status. For example, information on why processing might have failed or if the video was blocked. |
| thumbnail | Image | No | The URL of the thumbnail image of the video. The thumbnail image's URL must be an eBayPictureURL (EPS URL). |
| thumbnail.imageUrl | string | No | The URL of the image's location. |
| title | string | No | The title of the video. |
| videoId | string | No | The unique ID of the video. |
