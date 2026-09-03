---
title: getMotorsListingPolicies
category: Metadata_API
api_name: getMotorsListingPolicies
method: GET
path: /marketplace/{marketplace_id}/get_motors_listing_policies
---

**Category:** Metadata_API
**API:** getMotorsListingPolicies

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/marketplace/{marketplace_id}/get_motors_listing_policies

## API Description
This method returns eBay Motors policy metadata for all leaf categories on the specified marketplace. By default, this method returns metadata on all leaf categories. You can limit the size of the result set by using the filter query parameter to specify only the leaf category IDs you want to review. If you specify a valid marketplace ID but that marketplace does not contain policy information, or if you filter out all results, a successful call returns a 204 No content status code with an empty response body. Note: To return policy information for eBay US Motors categories, specify marketplace_id as EBAY_MOTORS_US .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| filter (query) | string | No | This query parameter limits the response by only returning metadata for the specified leaf categories. Supply the categoryId for one or more leaf categories. You can verify if a category is a leaf category by using the Taxonomy API and looking for a "leafCategory": true tag. The parameter takes a li |
| marketplace_id (path) | string | Yes | This path parameter specifies the eBay marketplace for which policy information is retrieved. See HTTP Request Headers for a list of supported eBay marketplace ID values. |
| Accept-Language (header) | string | No | This header is required to retrieve metadata for the French Canada, French Belgium, and Dutch Belgium marketplaces. Follow the instructions below to retrieve metadata for these three marketplaces: French Belgium : Set the marketplace_id path parameter value to EBAY_BE , and include the Accept-Langua |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| motorsListingPolicies | array<MotorsListingPolicy> | No | This array contains applicable policy metadata for the leaf categories returned for the marketplace specified in the path parameter marketplace_id and optionally limited by only those leaf category IDs specified in the query parameter filter . |
| motorsListingPolicies.categoryId | string | No | The unique identifier of the eBay leaf category for which metadata is being returned. |
| motorsListingPolicies.categoryTreeId | string | No | The unique identifier of the category tree. |
| motorsListingPolicies.depositSupported | boolean | No | This field is returned as true if the corresponding category supports the use of a deposit/down payment on a motor vehicle listing. In an AddItem call, the seller can configure a down payment for a motor vehicle listing using the PaymentDetails container. |
| motorsListingPolicies.ebayMotorsProAdFormatEnabled | string | No | Indicates whether or not eBay Motors Pro sellers can use classified ads in this category to sell their vehicles. This element is applicable for eBay Motors Pro users. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.ebayMotorsProAutoAcceptEnabled | boolean | No | Indicates whether or not the category supports the Best Offer Auto Accept feature for eBay Motors Pro listings. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProAutoDeclineEnabled | boolean | No | Indicates whether or not the category allows auto-decline for Best Offers for eBay Motors Classified Ad listings. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProBestOfferEnabled | string | No | This enumerated value indicates whether or not Best Offer features are supported for eBay Motors Classified Ad listings in this category. This element is for eBay Motors Pro users. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.ebayMotorsProCompanyNameEnabled | boolean | No | Indicates whether this category supports including the company name in the seller's contact information. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProContactByAddressEnabled | boolean | No | Indicates whether this category supports including the address in the seller's contact information. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProContactByEmailEnabled | boolean | No | Indicates whether this category supports including an email address in the seller's contact information. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProContactByPhoneEnabled | boolean | No | Indicates whether this category supports including the telephone in the seller's contact information. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProCounterOfferEnabled | boolean | No | Indicates whether counter offers are allowed on Best Offers for this category in an eBay Motors Classified Ad listing. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProPaymentMethodCheckOutEnabled | string | No | This enumerated value indicates whether this category supports that the payment method should be displayed to the user for this category in an eBay Motors Classified Ad listing. Even if enabled, checkout may or may not be enabled. This element is for eBay Motors Pro users. For implementation help, r |
| motorsListingPolicies.ebayMotorsProPhoneCount | integer | No | Indicates the number of phone numbers that can be included through contact information for this category. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProSellerContactDetailsEnabled | boolean | No | Indicates whether this category allows seller-level contact information for eBay Motors Classified Ad listings. A value of true means seller-level contact information is available for Classified Ad listings. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProShippingMethodEnabled | boolean | No | Indicates if shipping options should be displayed to the user for this category in an eBay Motors Classified Ad listing. This element is for eBay Motors Pro users. |
| motorsListingPolicies.ebayMotorsProStreetCount | integer | No | This field indicates the number of street addresses allowed in contact information for this category. This element is for eBay Motors Pro users. |
| motorsListingPolicies.epidSupported | boolean | No | If returned as true , this indicates the category supports the use of an eBay Product ID (e.g. ePID) to identify which motorcycles and/or scooters are compatible with a motor vehicle part or accessory. ePIDs can only be used to identify motorcycles and scooters on the Germany and UK sites. |
| motorsListingPolicies.kTypeSupported | boolean | No | This field indicates whether or not the category supports the use of a K type to identify the cars and trucks compatible with a motor vehicle part or accessory. Only the AU, DE, ES, FR, IT, and UK marketplaces support the use of K types. See Compatibility by K type for more information |
| motorsListingPolicies.localListingDistances | array<LocalListingDistance> | No | This array shows the supported distances (in miles) for different types of Local Market subscription types in this category. Motor vehicle listings will be shown to buyers located within these proximities of the vehicle's location. |
| motorsListingPolicies.localListingDistances.distances | array<integer> | No | This array indicates the radius (in miles) of the selling area for Local Market Vehicle listings. |
| motorsListingPolicies.localListingDistances.distanceType | string | No | This enumerated value indicates the type of local listing distances, such as non-subscription or regular, for items listed by sellers. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.localMarketAdFormatEnabled | string | No | Specifies whether this category supports Motor Local Market Classified Ad listings. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.localMarketAutoAcceptEnabled | boolean | No | Specifies whether this category supports auto-accept for Best Offers for Motors Local Market Classified Ads. |
| motorsListingPolicies.localMarketAutoDeclineEnabled | boolean | No | Specifies whether this category supports auto-decline for Best Offers for Motors Local Market Classified Ads. |
| motorsListingPolicies.localMarketBestOfferEnabled | string | No | Indicates if Best Offer is enabled/required for Motors Local Market Classified Ad listings in this category. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.localMarketCompanyNameEnabled | boolean | No | Indicates whether the category supports the seller's company name being specified when using Motors Local Market classified ads. |
| motorsListingPolicies.localMarketContactByAddressEnabled | boolean | No | Indicates whether this category supports including the address in the seller's contact information. |
| motorsListingPolicies.localMarketContactByEmailEnabled | boolean | No | Indicates whether the category supports including an email address in the seller's contact information. |
| motorsListingPolicies.localMarketContactByPhoneEnabled | boolean | No | Indicates whether this category supports including the telephone in the seller's contact information. |
| motorsListingPolicies.localMarketCounterOfferEnabled | boolean | No | Indicates whether counter offers are allowed on Best Offers for this category for Motors Local Market Classified Ad listings. |
| motorsListingPolicies.localMarketNonSubscription | boolean | No | Indicates whether the category supports a seller creating a Motors Local Market listing without a subscription. This feature is only available to licensed vehicle dealers. |
| motorsListingPolicies.localMarketPaymentMethodCheckOutEnabled | string | No | Indicates if the payment method should be displayed to the user for this category in an Motors Local Market Classified Ad listing. Even if enabled, checkout may or may not be enabled. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.localMarketPhoneCount | integer | No | Indicates the number of phone numbers that can be included through contact information for this category. |
| motorsListingPolicies.localMarketPremiumSubscription | boolean | No | Indicates whether the category supports the Premium level subscription Motors Local Market listings. This feature is only available to licensed vehicle dealers. |
| motorsListingPolicies.localMarketRegularSubscription | boolean | No | Indicates whether the category supports the Regular level subscription to Motors Local Market listings. This feature is only available to licensed vehicle dealers. |
| motorsListingPolicies.localMarketSellerContactDetailsEnabled | boolean | No | Specifies the whether this category allows seller-level contact information for Motors Local Market Classified Ad listings. |
| motorsListingPolicies.localMarketShippingMethodEnabled | boolean | No | Indicates if shipping methods should be displayed to the user for this category in an Motors Local Market Classified Ad listing. Even if enabled, checkout may or may not be enabled. |
| motorsListingPolicies.localMarketSpecialitySubscription | boolean | No | Indicates whether the category supports the Speciality level subscription to Motors Local Market listings. This feature is only available to licensed vehicle dealers. |
| motorsListingPolicies.localMarketStreetCount | integer | No | Indicates which address option is enabled for the seller's contact information. |
| motorsListingPolicies.maxGranularFitmentCount | integer | No | Indicates the maximum number of compatible applications allowed per item when adding or revising items with compatibilities provided at the most detailed granularity. For example, in Car and Truck Parts on the US site, the most granular application would include Year, Make, Model, Trim, and Engine. |
| motorsListingPolicies.maxItemCompatibility | integer | No | Indicates the maximum number of compatible applications allowed per item when adding or revising items. This is relevant for specifying parts compatibility by application manually only. See Specify parts compatibility manually and Managing product compatibility for more information. |
| motorsListingPolicies.minItemCompatibility | integer | No | Indicates the minimum number of required compatible applications for listing items. A value of 0 indicates it is not mandatory to specify parts compatibilities when listing. |
| motorsListingPolicies.nonSubscription | string | No | The value in this field indicates whether the category supports Motors Local Market listings if the seller does not have a vehicle subscription. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.premiumSubscription | string | No | The value in this field indicates whether the category supports Motors Local Market listings if the seller has a Premium vehicle subscription. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.regularSubscription | string | No | The value in this field indicates whether the category supports Motors Local Market listings if the seller has a Regular vehicle subscription. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.sellerProvidedTitleSupported | boolean | No | This field is returned as true if the corresponding category supports the use of a seller-provided title for a motor vehicle listing on the US or Canada Motors marketplaces. A seller-provided title is a descriptive title, given by the seller, that appears below eBay's pre-filled listing title for th |
| motorsListingPolicies.specialitySubscription | string | No | The value in this field indicates whether the category supports Motors Local Market listings if the seller has a Specialty vehicle subscription. For implementation help, refer to eBay API documentation |
| motorsListingPolicies.vinSupported | boolean | No | Indicates if Vehicle Identification Number is supported. |
| motorsListingPolicies.vrmSupported | boolean | No | Indicates if Vehicle Registration Mark is supported. |
| warnings | array<Error> | No | An array of the warnings that were generated as a result of the request. This field is not returned if no warnings were generated by the request. |
| warnings.category | string | No | The category type for this error or warning. It takes an ErrorCategory object which can have one of three values: Application : Indicates an exception or error occurred in the application code or at runtime. Examples include catching an exception in a service's business logic, system failures, or re |
| warnings.domain | string | No | Name of the domain containing the service or application. |
| warnings.errorId | integer | No | A positive integer that uniquely identifies the specific error condition that occurred. Your application can use error codes as identifiers in your customized error-handling algorithms. |
| warnings.inputRefIds | array<string> | No | Identifies specific request elements associated with the error, if any. inputRefId's response is format specific. For JSON, use JSONPath notation. |
| warnings.longMessage | string | No | An expanded version of message that should be around 100-200 characters long, but is not required to be such. |
| warnings.message | string | No | An end user and app developer friendly device agnostic message. It explains what the error or warning is, and how to fix it (in a general sense). Its value is at most 50 characters long. If applicable, the value is localized in the end user's requested locale. |
| warnings.outputRefIds | array<string> | No | Identifies specific response elements associated with the error, if any. Path format is the same as inputRefId . |
| warnings.parameters | array<ErrorParameter> | No | This optional complex field type contains a list of one or more context-specific ErrorParameter objects, with each item in the list entry being a parameter (or input field name) that caused an error condition. Each ErrorParameter object consists of two fields, a name and a value . |
| warnings.parameters.name | string | No | Name of the entity that threw the error. |
| warnings.parameters.value | string | No | A description of the error. |
| warnings.subdomain | string | No | Name of the domain's subsystem or subdivision. For example, checkout is a subdomain in the buying domain. |
