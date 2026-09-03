---
title: getItemSnapshotFeed
category: Item_Feed_Service
api_name: getItemSnapshotFeed
method: GET
path: /item_snapshot
---

**Category:** Item_Feed_Service
**API:** getItemSnapshotFeed

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/item_snapshot

## API Description
The Hourly Snapshot feed file is generated each hour every day for most categories. This method lets you download an Hourly Snapshot TSV_GZIP (tab-separated value gzip) feed file containing the details of all the items that have changed within the specified day and hour for a specific category. This means to generate the 8AM file of items that have changed from 8AM and 8:59AM, the service starts at 9AM. You can retrieve the 8AM snapshot file at 10AM. Snapshot feeds now include new listings. You can check itemCreationDate to identify listings that were newly created within the specified hour. Note: Filters are applied to the feed files. For details, see Feed File Filters . When curating the items returned, be sure to code as if these filters are not applied as they can be changed or removed in the future. You can use the response from this method to update the item details of items stored in your database. By looking at the value of itemSnapshotDate for a given item, you will be able to tell which information is the latest. Important: When the value of the availability column is UNAVAILABLE , only the itemId and availability columns are populated. Note: The downloaded file will be gzipped automatically, so there is no reason to supply Accept-Encoding:gzip as a header. If this header is supplied, the downloaded file will be compressed twice, and this has no extra benefit. Downloading feed files Hourly snapshot feed files are binary gzip files. If the file is larger than 100 MB, the download must be streamed in chunks. You specify the size of the chunks in bytes using the Range request header. The Content-range response header indicates where in the full resource this partial chunk of data belongs and the total number of bytes in the file. For more information about using these headers, see Retrieving a gzip feed file . Note: A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate errors that are returned in JSON format. For documentation purposes, the successful call response is shown below as JSON fields so that the value returned in each column can be explained. The order of the response fields shows the order of the columns in the feed file. Restrictions For a list of supported sites and other restrictions, see API Restrictions .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept (header) | string | Yes | The formats that the client accepts for the response. A successful call will always return a TSV.GZIP file; however, unsuccessful calls generate error codes that are returned in JSON format. Default: application/json,text/tab-separated-values |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | The ID of the eBay marketplace where the item is hosted. This value is case sensitive. For example: &nbsp;&nbsp; X-EBAY-C-MARKETPLACE-ID = EBAY_US For a list of supported sites see, API Restrictions . |
| Range (header) | string | Yes | This header specifies the range in bytes of the chunks of the gzip file being returned. Format: bytes= startpos - endpos For example, the following retrieves the first 10 MBs of the feed file. &nbsp;&nbsp; Range bytes=0-10485760 For more information about using this header, see Retrieving a gzip fee |
| category_id (query) | string | Yes | This query parameter specifies the eBay top-level category ID of the items to be returned in the feed file. The list of eBay category IDs changes over time and category IDs are not the same across all the eBay marketplaces. To get a list of the top-level categories for a marketplace, you can use the |
| snapshot_date (query) | string | Yes | This query parameter specifies the date and hour of the snapshot feed file you want to retrieve. Each file contains the items that changed within the hour in the specified category. So, the 9AM file contains the items that changed between 9AM and 9:59AM on the day specified. It takes 2 hours to gene |

## Response
_No documented response fields._
