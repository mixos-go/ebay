---
title: getShippingServices
category: Metadata_API
api_name: getShippingServices
method: GET
path: /shipping/marketplace/{marketplace_id}/get_shipping_services
---

**Category:** Metadata_API
**API:** getShippingServices

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/shipping/marketplace/{marketplace_id}/get_shipping_services

## API Description
This method retrieves a list of shipping services supported for the specified marketplace, including valid shipping services, shipping times, and package constraints such as size and weight. Manage shipping services using business policies through the fulfillment_policy resource of the Account v1 API .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which shipping services information is retrieved. See MarketplaceIdEnum for supported eBay marketplace ID values. Note: When listing the items on the French Canada, French Belgium, and Dutch Belgium marketplaces, also set the Accept-Language hea |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shippingServices | array<ShippingService> | No | A complete list of shipping service options that can be used on the marketplace for shipping items. |
| shippingServices.description | string | No | This field returns the localized name of the shipping service. |
| shippingServices.internationalService | boolean | No | A value of true indicates that the shipping service is international. An international shipping service option is required if an item is being shipped from one country (origin) to another (destination). |
| shippingServices.maxShippingTime | integer | No | This value indicates the maximum number of business days that it takes the shippingCarrier to ship an item using the corresponding shippingService . |
| shippingServices.minShippingTime | integer | No | This value indicates the minimum number of business days that it takes the shippingCarrier to ship an item using the corresponding shippingService . |
| shippingServices.packageLimits | PackageLimits | No | This container provides name-value pairs that specify physical constraints and measurement units of packages for the shippingCarrier and the corresponding shippingService . An empty container is returned if the shipping service does not have any package limits defined. |
| shippingServices.packageLimits.dimensionUnit | string | No | Unit of dimensional measurement, for example INCH or CENTIMETER . |
| shippingServices.packageLimits.maxGirth | number | No | The maximum girth allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.maxHeight | number | No | The maximum height allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.maxLength | number | No | The maximum length allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.maxWeight | number | No | The maximum weight allowed for a package shipped through the corresponding shipping service, as measured in units of weightUnit . |
| shippingServices.packageLimits.maxWidth | number | No | The maximum width allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.minGirth | number | No | The minimum girth allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.minHeight | number | No | The minimum height allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.minLength | number | No | The minimum length allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.minWeight | number | No | The minimum weight allowed for a package shipped through the corresponding shipping service, as measured in units of weightUnit . |
| shippingServices.packageLimits.minWidth | number | No | The minimum width allowed for a package shipped through the corresponding shipping service, as measured in units of dimensionUnit . |
| shippingServices.packageLimits.weightUnit | string | No | Unit of weight measurement, for example KILOGRAM or OUNCE . |
| shippingServices.shippingCarrier | string | No | The code for the shipping carrier returned, for example, UPS , FedEx , and USPS . |
| shippingServices.shippingCategory | string | No | The shipping category of the shipping service including: ECONOMY , STANDARD , EXPEDITED , ONE_DAY , PICKUP , and other similar categories. |
| shippingServices.shippingCostTypes | array<string> | No | A list of shipping cost types that this shipping service option supports. For example, FLAT_RATE , CALCULATED , and FREIGHT . |
| shippingServices.shippingService | string | No | The name of the shipping service. The shipping service named here can only be used in listings or in business policies if validForSellingFlow is true . The value returned in this field is used in listing APIs and business policies to set the shipping service. |
| shippingServices.validForSellingFlow | boolean | No | A value of true indicates that the shippingService can be set as an available shipping service in the listing or through the fulfillment business policy. |
