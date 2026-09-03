---
title: getItemPriorityFeed
category: Item_Feed_Service
api_name: getItemPriorityFeed
method: GET
path: /item_priority
---

**Category:** Item_Feed_Service
**API:** getItemPriorityFeed

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/item_priority

## API Description
Using this method, you can download a TSV_GZIP (tab separated value gzip) Item Priority feed file, which allows you to track changes (deltas) in the status of your priority items, such as when an item is added or removed from a campaign. The delta feed tracks the changes to the status of items within a category you specify in the input URI. You can also specify a specific date for the feed you want returned. Important! You must consume the daily feeds ( Item , Item Group ) before consuming the Item Priority feed. This ensures that your inventory is up to date. Note: The downloaded file will be gzipped automatically, so there is no reason to supply Accept-Encoding:gzip as a header. If this header is supplied, the downloaded file will be compressed twice, and this has no extra benefit. Downloading feed files Note: Filters are applied to the feed files. For details, see Feed File Filters . When curating the items returned, be sure to code as if these filters are not applied as they can be changed or removed in the future. Priority Item feed files are binary gzip files. If the file is larger than 100 MB, the download must be streamed in chunks. You specify the size of the chunks in bytes using the Range request header. The Content-range response header indicates where in the full resource this partial chunk of data belongs and the total number of bytes in the file. For more information about using these headers, see Retrieve a gzip feed file . In addition to the API, there is an open source Feed SDK written in Java that downloads, combines files into a single file when needed, and unzips the entire feed file. It also lets you specify field filters to curate the items in the file. Note: A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate errors that are returned in JSON format. For documentation purposes, the successful call response is shown below as JSON fields so that the value returned in each column can be explained. The order of the response fields shows the order of the columns in the feed file. Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept (header) | string | Yes | The formats that the client accepts for the response. A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate error codes that are returned in JSON format. Default: application/json,text/tab-separated-values |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the item is hosted. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, Buy API Support by Marketplace . |
| Range (header) | string | Yes | Header specifying content range to be retrieved. Only supported range is bytes. Example : bytes = 0-102400 . |
| category_id (query) | string | Yes | This query parameter specifies the eBay top-level category ID of the items to be returned in the feed file. The list of eBay category IDs changes over time and category IDs are not the same across all the eBay marketplaces. To get a list of the top-level categories for a marketplaces, you can use th |
| date (query) | string | Yes | This query parameter specifies the date of the feed you want returned. This can be up to 14 days in the past but cannot be set to a date in the future. Format: yyyyMMdd Note: The daily Item feed files are available each day after 9AM MST (US Mountain Standard Time), which is -7 hours UTC time. There |

## Response
_No documented response fields._
