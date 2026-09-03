---
title: getCharityOrg
category: Charity_API
api_name: getCharityOrg
method: GET
path: /charity_org/{charity_org_id}
---

**Category:** Charity_API
**API:** getCharityOrg

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/charity_org/{charity_org_id}

## API Description
This call is used to retrieve detailed information about supported charitable organizations. It allows users to retrieve the details for a specific charitable organization using its charity organization ID.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| charity_org_id (path) | string | Yes | The unique ID of the charitable organization. |
| X-EBAY-C-MARKETPLACE-ID (header) | string | Yes | A header used to specify the eBay marketplace ID. Valid Values: EBAY_GB and EBAY_US |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| charityOrgId | string | No | The ID of the charitable organization. |
| description | string | No | The description of the charitable organization. |
| location | Location | No | The location details of the charitable organization. |
| location.address | Address | No | The address of the charitable organization. |
| location.address.city | string | No | The city of the charitable organization. |
| location.address.stateOrProvince | string | No | The state or province of the charitable organization. |
| location.address.postalCode | string | No | The postal code of the charitable organization. |
| location.address.country | string | No | The two-letter ISO 3166 standard of the country of the address. For implementation help, refer to eBay API documentation |
| location.geoCoordinates | GeoCoordinates | No | The geo-coordinates of the charitable organization. |
| location.geoCoordinates.latitude | number | No | The latitude component of the geographic coordinate. |
| location.geoCoordinates.longitude | number | No | The longitude component of the geographic coordinate. |
| logoImage | Image | No | The logo of the charitable organization. |
| logoImage.height | string | No | The height of the logo image. |
| logoImage.imageUrl | string | No | The URL to the logo image location. |
| logoImage.width | string | No | The width of the logo image. |
| missionStatement | string | No | The mission statement of the charitable organization. |
| name | string | No | The name of the charitable organization. |
| registrationId | string | No | The registration ID for the charitable organization. Note: For the US marketplace, this is the EIN. |
| website | string | No | The link to the website for the charitable organization. |
