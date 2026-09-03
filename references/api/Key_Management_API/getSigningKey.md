---
title: getSigningKey
category: Key_Management_API
api_name: getSigningKey
method: GET
path: /signing_key/{signing_key_id}
---

**Category:** Key_Management_API
**API:** getSigningKey

**Method:** GET
**HTTP Path:** https://apiz.ebay.com{basePath}/signing_key/{signing_key_id}

## API Description
This method returns the Public Key , Public Key as JWE , and metadata for a specified signingKeyId associated with the application key making the call. Note: It is important to note that the privateKey value is not returned. In order to further ensure the security of confidential client information, eBay does not store the privateKey value in any system. If a developer loses their privateKey they must generate new keypairs using the createSigningKey method.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| signing_key_id (path) | string | Yes | The system-generated eBay ID of the keypairs being requested. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| creationTime | integer | No | The UNIX timestamp when the SigningKey was created. This time is represented as the number of seconds from "1970-01-01T00:00:00Z", as measured in UTC, until the date and time the SigningKey was created. |
| expirationTime | integer | No | The UNIX timestamp when the SigningKey expires. This time is represented as the number of seconds from "1970-01-01T00:00:00Z", as measured in UTC, until the date and time the SigningKey expires. Note: All keys have an expiration date of three (3) years after their creationTime . |
| jwe | string | No | This is the JSON Web Encrypted (JWE) value for the publicKey . |
| privateKey | string | No | This is the Private Key that has been generated using the specified signingKeyCipher . Note: The privateKey value will only be returned in the response payload of the createSigningKey method. It will never be returned by the getSigningKey or getSigningKeys methods. Developers are strongly advised to |
| publicKey | string | No | This is the Public Key that has been generated using the specified signingKeyCipher . As a matter of good practice, developers are strongly advised to download this value and store it locally for safe-keeping and future reference. |
| signingKeyCipher | string | No | Indicates the cipher used to create the keypairs. Refer to SigningKeyCiper for the list of supported enum values. For implementation help, refer to eBay API documentation |
| signingKeyId | string | No | The system-generated eBay ID for the keypairs. |
