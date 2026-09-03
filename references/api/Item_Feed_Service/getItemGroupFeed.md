---
title: getItemGroupFeed
category: Item_Feed_Service
api_name: getItemGroupFeed
method: GET
path: /item_group
---

**Category:** Item_Feed_Service
**API:** getItemGroupFeed

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/item_group

## API Description
This method lets you download a TSV_GZIP (tab separated value gzip) Item Group feed file. An item group is an item that has various aspect differences, such as color, size, storage capacity, etc. There are two types of item group feed files generated: A daily Item Group feed file containing the item group variation information associated with items returned in the Item feed file for a specific day, category, and marketplace. ( feed_scope = NEWLY_LISTED ) A weekly Item Group Bootstrap feed file containing all the item group variation information associated with items returned in the Item Bootstrap feed file for all the items in a specific category. ( feed_scope = ALL_ACTIVE ) Note: Filters are applied to the feed files. For details, see Feed File Filters . When curating the items returned, be sure to code as if these filters are not applied as they can be changed or removed in the future. Note: The downloaded file will be gzipped automatically, so there is no reason to supply Accept-Encoding:gzip as a header. If this header is supplied, the downloaded file will be compressed twice, and this has no extra benefit. The contents of these feed files are based on the contents of the corresponding daily Item or Item Bootstrap feed file. When a new Item or Item Bootstrap feed file is generated, the service reads the file and if an item in the file has a primaryItemGroupId value, which indicates the item is part of an item group, it uses that value to return the item group (parent item) information for that item in the corresponding Item Group or Item Group Bootstrap feed file. This information includes the name/value pair of the aspects of the items in this group returned in the variesByLocalizedAspects column. For example, if the item was a shirt some of the variation names could be Size, Color, etc. Also the images for the various aspects are returned in the additionalImageUrls column. The first line in any feed file is the header, which labels the columns and indicates the order of the values on each line. Each header is described in the Response fields section. Combining the Item Group and Item feed files The Item Group or Item Group Bootstrap feed file contains details about the item group (parent item), including the item group ID itemGroupId . You match the value of itemGroupId from the Item Group feed file with the value of primaryItemGroupId from the corresponding daily Item or Item Bootstrap feed file. Downloading feed files Item Group feed files are binary gzip files. If the file is larger than 100 MB, the download must be streamed in chunks. You specify the size of the chunks in bytes using the Range request header. The content-range response header indicates where in the full resource this partial chunk of data belongs and the total number of bytes in the file. For more information about using these headers, see Retrieve a gzip feed file . Note: A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate errors that are returned in JSON format. For documentation purposes, the successful call response is shown below as JSON fields so that the value returned in each column can be explained. The order of the response fields shows the order of the columns in the feed file. Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept (header) | string | Yes | The formats that the client accepts for the response. A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate error codes that are returned in JSON format. Default: application/json,text/tab-separated-values |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the item is hosted. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, API Restrictions . |
| Range (header) | string | No | This header specifies the range in bytes of the chunks of the gzip file being returned. Format: bytes= startpos - endpos For example, the following retrieves the first 10 MBs of the feed file. &nbsp;&nbsp; Range bytes=0-10485760 For more information about using this header, see Retrieving a gzip fee |
| feed_scope (query) | string | Yes | This query parameter specifies the type of file to return. Valid Values: NEWLY_LISTED - Returns the Item Group feed file containing the item group variation information for items in the daily Item feed file that were associated with an item group. The items in this type of Item feed file are items t |
| category_id (query) | string | Yes | This query parameter specifies eBay top-level category ID of the items to be returned in the feed file. The list of eBay category IDs changes over time and category IDs are not the same across all the eBay marketplaces. To get a list of the top-level categories for a marketplaces, you can use the Ta |
| date (query) | string | No | This query parameter specifies the date of the daily Item Group feed file ( feed_scope = NEWLY_LISTED ) you want. The date is required only for the daily Item Group feed file. If you specify a date for the Item Group Bootstrap file ( feed_scope = ALL_ACTIVE ), the date is ignored and the latest file |

## Response
_No documented response fields._
