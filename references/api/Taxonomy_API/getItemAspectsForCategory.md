---
title: getItemAspectsForCategory
category: Taxonomy_API
api_name: getItemAspectsForCategory
method: GET
path: /category_tree/{category_tree_id}/get_item_aspects_for_category
---

**Category:** Taxonomy_API
**API:** getItemAspectsForCategory

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/get_item_aspects_for_category

## API Description
This call returns a list of aspects that are appropriate or necessary for accurately describing items in the specified leaf category. Each aspect identifies an item attribute (for example, color,) for which the seller will be required or encouraged to provide a value (or variation values) when offering an item in that category on eBay. For each aspect, getItemAspectsForCategory provides complete metadata, including: The aspect's data type, format, and entry mode Whether the aspect is required in listings Whether the aspect can be used for item variations Whether the aspect accepts multiple values for an item Allowed values for the aspect Use this information to construct an interface through which sellers can enter or select the appropriate values for their items or item variations. Once you collect those values, include them as product aspects when creating inventory items using the Inventory API.

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_id (query) | string | Yes | The unique identifier of the leaf category for which aspects are being requested. Note: If the category_id submitted does not identify a leaf node of the tree, this call returns an error. |
| category_tree_id (path) | string | Yes | The unique identifier of the eBay category tree. The category tree ID for an eBay marketplace can be retrieved using the getDefaultCategoryTreeId method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| aspects | array<Aspect> | No | A list of item aspects (for example, color) that are appropriate or necessary for accurately describing items in a particular leaf category. Each category has a different set of aspects and different requirements for aspect values. Sellers are required or encouraged to provide one or more acceptable |
| aspects.aspectConstraint | AspectConstraint | No | Information about the formatting, occurrence, and support of this aspect. |
| aspects.aspectConstraint.aspectApplicableTo | array<string> | No | This value indicate if the aspect identified by the aspects.localizedAspectName field is a product aspect (relevant to catalog products in the category) or an item/instance aspect, which is an aspect whose value will vary based on a particular instance of the product. |
| aspects.aspectConstraint.aspectDataType | string | No | The data type of this aspect. For implementation help, refer to eBay API documentation |
| aspects.aspectConstraint.aspectEnabledForVariations | boolean | No | A value of true indicates that this aspect can be used to help identify item variations. |
| aspects.aspectConstraint.aspectFormat | string | No | Returned only if the value of aspectDataType identifies a data type that requires specific formatting. Currently, this field provides formatting hints as follows: DATE : YYYY , YYYYMM , YYYYMMDD NUMBER : int32 , double |
| aspects.aspectConstraint.aspectMaxLength | integer | No | The maximum length of the item/instance aspect's value. The seller must make sure not to exceed this length when specifying the instance aspect's value for a product. This field is only returned for instance aspects. |
| aspects.aspectConstraint.aspectMode | string | No | The manner in which values of this aspect must be specified by the seller (as free text or by selecting from available options). For implementation help, refer to eBay API documentation |
| aspects.aspectConstraint.aspectRequired | boolean | No | A value of true indicates that this aspect is required when offering items in the specified category. |
| aspects.aspectConstraint.aspectUsage | string | No | The enumeration value returned in this field will indicate if the corresponding aspect is recommended or optional. Note: This field is always returned, even for hard-mandated/required aspects (where aspectRequired : true ). The value returned for required aspects will be RECOMMENDED , but they are a |
| aspects.aspectConstraint.expectedRequiredByDate | string | No | The expected date after which the aspect will be required. Note: The value returned in this field specifies only an approximate date, which may not reflect the actual date after which the aspect is required. |
| aspects.aspectConstraint.itemToAspectCardinality | string | No | Indicates whether this aspect can accept single or multiple values for items in the specified category. Note: Up to 30 values can be supplied for aspects that accept multiple values. For implementation help, refer to eBay API documentation |
| aspects.aspectConstraint.aspectAdvancedDataType | string | No | Indicates additional data type requirements for the aspect. For example, NUMERIC_RANGE indicates that the aspect value must be in numeric range format. Note: Currently only NUMERIC_RANGE is supported. For implementation help, refer to eBay API documentation |
| aspects.aspectValues | array<AspectValue> | No | A list of valid values for this aspect (for example: Red , Green , and Blue ), along with any constraints on those values. |
| aspects.aspectValues.localizedValue | string | No | The localized value of this aspect. Note: This value is always localized for the specified marketplace. |
| aspects.aspectValues.valueConstraints | array<ValueConstraint> | No | Not returned if the value of the localizedValue field can always be selected for this aspect of the specified category. Contains a list of the dependencies that identify when the value of the localizedValue field is available for the current aspect. Each dependency specifies the values of another as |
| aspects.aspectValues.valueConstraints.applicableForLocalizedAspectName | string | No | The name of the control aspect on which the current aspect value depends. |
| aspects.aspectValues.valueConstraints.applicableForLocalizedAspectValues | array<string> | No | Contains a list of the values of the control aspect on which this aspect's value depends. When the control aspect has any of the specified values, the current value of the current aspect will also be available. |
| aspects.localizedAspectName | string | No | The localized name of this aspect (for example: Colour on the eBay UK site). Note: This name is always localized for the specified marketplace. |
| aspects.relevanceIndicator | RelevanceIndicator | No | The relevance of this aspect. This field is returned if eBay has data on how many searches have been performed for listings in the category using this item aspect. Note: This container is restricted to applications that have been granted permission to access this feature. You must submit an App Chec |
| aspects.relevanceIndicator.searchCount | integer | No | The number of recent searches (based on 30 days of data) for the aspect. |
