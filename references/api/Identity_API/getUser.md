---
title: getUser
category: Identity_API
api_name: getUser
method: GET
path: /user/
---

**Category:** Identity_API
**API:** getUser

**Method:** GET
**HTTP Path:** https://apiz.ebay.com{basePath}/user/

## API Description
This method retrieves the account profile information for an authenticated user, which requires a User access token . What is returned is controlled by the scopes . For a business account you use the default scope commerce.identity.readonly , which returns all the fields in the businessAccount container. These are returned because this is all public information. For an individual account, the fields returned in the individualAccount container are based on the scope you use. Using the default scope, only public information, such as eBay user ID, are returned. For details about what each scope returns, see the Identity API Overview . In the Sandbox, this API returns mock data. Note: You must use the correct scope or scopes for the data you want returned.

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| accountType | string | No | Indicates the user account type. This is determined when the user registers with eBay. If they register for a business account, this value will be BUSINESS. If they register for a private account, this value will be INDIVIDUAL. This designation is required by the tax laws in the following countries: |
| businessAccount | BusinessAccount | No | The container that returns the business account information of the user. |
| businessAccount.address | Address | No | The container that returns the address of the business account. |
| businessAccount.address.addressLine1 | string | No | The first line of the street address. |
| businessAccount.address.addressLine2 | string | No | The second line of the street address. This field is not always used, but can be used for 'Suite Number' or 'Apt Number'. |
| businessAccount.address.city | string | No | The city of the address. |
| businessAccount.address.country | string | No | The two-letter ISO 3166 standard of the country of the address. For implementation help, refer to eBay API documentation |
| businessAccount.address.county | string | No | The county of the address. |
| businessAccount.address.postalCode | string | No | The postal code of the address. |
| businessAccount.address.stateOrProvince | string | No | The state or province of the address. |
| businessAccount.doingBusinessAs | string | No | An additional name that is used for their business on eBay. The business name is returned in the name field. |
| businessAccount.email | string | No | The email address of the business account. |
| businessAccount.name | string | No | The business name associated with the user's eBay account. |
| businessAccount.primaryContact | Contact | No | The container that returns the contact details of the person who is the primary contact for this account. |
| businessAccount.primaryContact.firstName | string | No | The first name of the contact person. |
| businessAccount.primaryContact.lastName | string | No | The last name of the contact person. |
| businessAccount.primaryPhone | Phone | No | The container that returns the primary phone number for the business account. |
| businessAccount.primaryPhone.countryCode | string | No | The two-letter ISO 3166 standard of the country to which the phone number belongs. |
| businessAccount.primaryPhone.number | string | No | The numeric string representing the phone number. |
| businessAccount.primaryPhone.phoneType | string | No | The type of phone service. Valid Values: MOBILE or LAND_LINE Code so that your app gracefully handles any future changes to this list. |
| businessAccount.secondaryPhone | Phone | No | The container that returns the secondary phone number for the business account. |
| businessAccount.secondaryPhone.countryCode | string | No | The two-letter ISO 3166 standard of the country to which the phone number belongs. |
| businessAccount.secondaryPhone.number | string | No | The numeric string representing the phone number. |
| businessAccount.secondaryPhone.phoneType | string | No | The type of phone service. Valid Values: MOBILE or LAND_LINE Code so that your app gracefully handles any future changes to this list. |
| businessAccount.website | string | No | The business website address associated with the eBay account. |
| individualAccount | IndividualAccount | No | The account information of the user. |
| individualAccount.email | string | No | The eBay user's registration email address. |
| individualAccount.firstName | string | No | The eBay user's first name. |
| individualAccount.lastName | string | No | The eBay user's last name. |
| individualAccount.primaryPhone | Phone | No | The container that returns the eBay user's primary phone number information. |
| individualAccount.primaryPhone.countryCode | string | No | The two-letter ISO 3166 standard of the country to which the phone number belongs. |
| individualAccount.primaryPhone.number | string | No | The numeric string representing the phone number. |
| individualAccount.primaryPhone.phoneType | string | No | The type of phone service. Valid Values: MOBILE or LAND_LINE Code so that your app gracefully handles any future changes to this list. |
| individualAccount.registrationAddress | Address | No | The container that returns the eBay user's address information. |
| individualAccount.registrationAddress.addressLine1 | string | No | The first line of the street address. |
| individualAccount.registrationAddress.addressLine2 | string | No | The second line of the street address. This field is not always used, but can be used for 'Suite Number' or 'Apt Number'. |
| individualAccount.registrationAddress.city | string | No | The city of the address. |
| individualAccount.registrationAddress.country | string | No | The two-letter ISO 3166 standard of the country of the address. For implementation help, refer to eBay API documentation |
| individualAccount.registrationAddress.county | string | No | The county of the address. |
| individualAccount.registrationAddress.postalCode | string | No | The postal code of the address. |
| individualAccount.registrationAddress.stateOrProvince | string | No | The state or province of the address. |
| individualAccount.secondaryPhone | Phone | No | The container that returns the eBay user's secondary phone number information. |
| individualAccount.secondaryPhone.countryCode | string | No | The two-letter ISO 3166 standard of the country to which the phone number belongs. |
| individualAccount.secondaryPhone.number | string | No | The numeric string representing the phone number. |
| individualAccount.secondaryPhone.phoneType | string | No | The type of phone service. Valid Values: MOBILE or LAND_LINE Code so that your app gracefully handles any future changes to this list. |
| registrationMarketplaceId | string | No | The eBay site on which the account is registered. For implementation help, refer to eBay API documentation |
| status | string | No | Indicates the user's account status. Possible values: CONFIRMED , UNCONFIRMED , ACCOUNTONHOLD and UNDETERMINED . For implementation help, refer to eBay API documentation |
| userId | string | No | The eBay immutable user ID of the user's account and can always be used to identify the user. |
| username | string | No | The user name, which was specific by the user when they created the account. Note: This value can be changed by the user. |
