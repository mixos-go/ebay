---
title: getItemFeed
category: Item_Feed_Service
api_name: getItemFeed
method: GET
path: /item
---

**Category:** Item_Feed_Service
**API:** getItemFeed

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/item

## API Description
This method lets you download a TSV_GZIP (tab separated value gzip) Item feed file. The feed file contains all the items from all the child categories of the specified category. The first line of the file is the header, which labels the columns and indicates the order of the values on each line. Each header is described in the Response fields section. There are two types of item feed files generated: A daily Item feed file containing all the newly listed items for a specific category, date, and marketplace ( feed_scope = NEWLY_LISTED ) A weekly Item Bootstrap feed file containing all the items in a specific category and marketplace ( feed_scope = ALL_ACTIVE ) Note: Filters are applied to the feed files. For details, see Feed File Filters . When curating the items returned, be sure to code as if these filters are not applied as they can be changed or removed in the future. Note: The downloaded file will be gzipped automatically, so there is no reason to supply Accept-Encoding:gzip as a header. If this header is supplied, the downloaded file will be compressed twice, and this has no extra benefit. Downloading feed files Item feed files are binary gzip files. If the file is larger than 100 MB, the download must be streamed in chunks. You specify the size of the chunks in bytes using the Range request header. The Content-range response header indicates where in the full resource this partial chunk of data belongs and the total number of bytes in the file.For more information about using these headers, see Retrieve a gzip feed file . In addition to the API, there is an open source Feed SDK written in Java that downloads, combines files into a single file when needed, and unzips the entire feed file. It also lets you specify field filters to curate the items in the file. Note: A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate errors that are returned in JSON format. For documentation purposes, the successful call response is shown below as JSON fields so that the value returned in each column can be explained. The order of the response fields shows the order of the columns in the feed file. Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept (header) | string | Yes | The formats that the client accepts for the response. A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate errors that are returned in JSON format. Default: application/json,text/tab-separated-values |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the item is hosted. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, API Restrictions . |
| Range (header) | string | Yes | This header specifies the range in bytes of the chunks of the gzip file being returned. Format: bytes= startpos - endpos For example, the following retrieves the first 10 MBs of the feed file. &nbsp;&nbsp; Range bytes=0-10485760 For more information about using this header, see Retrieving a gzip fee |
| feed_scope (query) | string | Yes | This query parameter specifies the type of feed file to return. Valid Values: NEWLY_LISTED - Returns the daily Item feed file containing all Good 'Til Cancelled items that were listed on the day specified by the date parameter in the category specified by the category_id parameter. ALL_ACTIVE - Retu |
| category_id (query) | string | Yes | This query parameter specifies the eBay top-level category ID of the items to be returned in the feed file. The list of eBay category IDs changes over time and category IDs are not the same across all the eBay marketplaces. To get a list of the top-level categories for a marketplace, you can use the |
| date (query) | string | No | This query parameter specifies the date of the daily Item feed file ( feed_scope = NEWLY_LISTED ) you want to retrieve. The date is required only for the daily Item feed file. If you specify a date for the Item Bootstrap file ( feed_scope = ALL_ACTIVE ), the date is ignored and the latest file is re |

## Response
_No documented response fields._
