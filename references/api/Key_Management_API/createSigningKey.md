---
title: createSigningKey
category: Key_Management_API
api_name: createSigningKey
method: POST
path: /signing_key
---

**Category:** Key_Management_API
**API:** createSigningKey

**Method:** POST
**HTTP Path:** https://apiz.ebay.com{basePath}/signing_key

## API Description
This method creates keypairs using one of the following ciphers: ED25519 (Edwards Curve) RSA Note: The recommended signature cipher is ED25519 (Edwards Curve) since it uses much shorter keys and therefore decreases the header size. However, for development frameworks that do not support ED25519, RSA is also supported. Following a successful completion, the following keys are returned: Private Key Public Key Public Key as JWE Once keypairs are created, developers are strongly advised to create and store a local copy of each keypair for future reference. Although the Public Key , Public Key as JWE , and metadata for keypairs may be retrieved by the getSigningKey and getSigningKeys methods, in order to further ensure the security of confidential client information, eBay does not store the Private Key value in any system. If a developer loses their Private Key they must generate new keypairs using the createSigningKey method. Note: For additional information about using keypairs, refer to Digital Signatures for APIs .

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Content-Type (header) | string | Yes | This header indicates the format of the request body provided by the client. Its value should be set to application/json . For more information, refer to HTTP request headers . |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| signingKeyCipher | string | No | The enumerated value for the cipher to be used to create the signing key. Refer to SigningKeyCiper for the list of supported enum values. For implementation help, refer to eBay API documentation |

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
