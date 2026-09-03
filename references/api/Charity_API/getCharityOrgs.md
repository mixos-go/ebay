---
title: getCharityOrgs
category: Charity_API
api_name: getCharityOrgs
method: GET
path: /charity_org
---

**Category:** Charity_API
**API:** getCharityOrgs

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/charity_org

## API Description
This call is used to search for supported charitable organizations. It allows users to search for a specific charitable organization, or for multiple charitable organizations, from a particular charitable domain and/or geographical region, or by using search criteria. The call returns paginated search results containing the charitable organizations that match the specified criteria.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | The number of items, from the result set, returned in a single page. Valid Values: 1-100 Default: 20 |
| offset (query) | string | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| q (query) | string | No | A query string that matches the keywords in name, mission statement, or description. |
| registration_ids (query) | string | No | A comma-separated list of charitable organization registration IDs. Note: Do not specify this parameter for query-based searches. Specify either the q or registration_ids parameter, but not both. Maximum Limit: 20 |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | A header used to specify the eBay marketplace ID. Valid Values: EBAY_GB and EBAY_US |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| charityOrgs | array<CharityOrg> | No | The list of charitable organizations that match the search criteria. |
| charityOrgs.charityOrgId | string | No | The ID of the charitable organization. |
| charityOrgs.description | string | No | The description of the charitable organization. |
| charityOrgs.location | Location | No | The location details of the charitable organization. |
| charityOrgs.location.address | Address | No | The address of the charitable organization. |
| charityOrgs.location.address.city | string | No | The city of the charitable organization. |
| charityOrgs.location.address.stateOrProvince | string | No | The state or province of the charitable organization. |
| charityOrgs.location.address.postalCode | string | No | The postal code of the charitable organization. |
| charityOrgs.location.address.country | string | No | The two-letter ISO 3166 standard of the country of the address. For implementation help, refer to eBay API documentation |
| charityOrgs.location.geoCoordinates | GeoCoordinates | No | The geo-coordinates of the charitable organization. |
| charityOrgs.location.geoCoordinates.latitude | number | No | The latitude component of the geographic coordinate. |
| charityOrgs.location.geoCoordinates.longitude | number | No | The longitude component of the geographic coordinate. |
| charityOrgs.logoImage | Image | No | The logo of the charitable organization. |
| charityOrgs.logoImage.height | string | No | The height of the logo image. |
| charityOrgs.logoImage.imageUrl | string | No | The URL to the logo image location. |
| charityOrgs.logoImage.width | string | No | The width of the logo image. |
| charityOrgs.missionStatement | string | No | The mission statement of the charitable organization. |
| charityOrgs.name | string | No | The name of the charitable organization. |
| charityOrgs.registrationId | string | No | The registration ID for the charitable organization. Note: For the US marketplace, this is the EIN. |
| charityOrgs.website | string | No | The link to the website for the charitable organization. |
| href | string | No | The relative path to the current set of results. |
| limit | integer | No | The number of items, from the result set, returned in a single page. Valid Values: 1-100 Default: 20 |
| next | string | No | The relative path to the next set of results. |
| offset | integer | No | The number of items that will be skipped in the result set. This is used with the limit field to control the pagination of the output. For example, if the offset is set to 0 and the limit is set to 10 , the method will retrieve items 1 through 10 from the list of items returned. If the offset is set |
| prev | string | No | The relative path to the previous set of results. |
| total | integer | No | The total number of matches for the search criteria. |
