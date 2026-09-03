---
title: Get_Aspects_for_All_Leaf_Categories_in_a_Marketplace
category: Taxonomy_API
api_name: Get_Aspects_for_All_Leaf_Categories_in_a_Marketplace
method: GET
path: /category_tree/{category_tree_id}/fetch_item_aspects
---

**Category:** Taxonomy_API
**API:** Get_Aspects_for_All_Leaf_Categories_in_a_Marketplace

**Method:** GET
**HTTP Path:** https://api.ebay.com{basePath}/category_tree/{category_tree_id}/fetch_item_aspects

## API Description
Get Aspects for All Leaf Categories in a Marketplace

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| category_tree_id (path) | string | Yes | The unique identifier of the eBay category tree. The category tree ID for an eBay marketplace can be retrieved using the getDefaultCategoryTreeId method. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| categoryTreeId | string | No | The unique identifier of the eBay category tree being requested. |
| categoryTreeVersion | string | No | The version of the category tree that is returned in the categoryTreeId field. |
| categoryAspects | array<CategoryAspect> | No | An array of aspects that are appropriate or necessary for accurately describing items in a particular leaf category. |
| categoryAspects.category | Category | No | The details that are appropriate or necessary to accurately define the category. |
| categoryAspects.category.categoryId | string | No | The unique identifier of the eBay category within its category tree. Note: The root node of a full default category tree includes the categoryId field, but its value should not be relied upon. It provides no useful information for application development. |
| categoryAspects.category.categoryName | string | No | The name of the category identified by categoryId . |
| categoryAspects.aspects | array<Aspect> | No | A list of aspect metadata that is used to describe the items in a particular leaf category. |
| categoryAspects.aspects.aspectConstraint | AspectConstraint | No | Information about the formatting, occurrence, and support of this aspect. |
| categoryAspects.aspects.aspectConstraint.aspectApplicableTo | array<string> | No | This value indicate if the aspect identified by the aspects.localizedAspectName field is a product aspect (relevant to catalog products in the category) or an item/instance aspect, which is an aspect whose value will vary based on a particular instance of the product. |
| categoryAspects.aspects.aspectConstraint.aspectDataType | string | No | The data type of this aspect. For implementation help, refer to eBay API documentation |
| categoryAspects.aspects.aspectConstraint.aspectEnabledForVariations | boolean | No | A value of true indicates that this aspect can be used to help identify item variations. |
| categoryAspects.aspects.aspectConstraint.aspectFormat | string | No | Returned only if the value of aspectDataType identifies a data type that requires specific formatting. Currently, this field provides formatting hints as follows: DATE : YYYY , YYYYMM , YYYYMMDD NUMBER : int32 , double |
| categoryAspects.aspects.aspectConstraint.aspectMaxLength | integer | No | The maximum length of the item/instance aspect's value. The seller must make sure not to exceed this length when specifying the instance aspect's value for a product. This field is only returned for instance aspects. |
| categoryAspects.aspects.aspectConstraint.aspectMode | string | No | The manner in which values of this aspect must be specified by the seller (as free text or by selecting from available options). For implementation help, refer to eBay API documentation |
| categoryAspects.aspects.aspectConstraint.aspectRequired | boolean | No | A value of true indicates that this aspect is required when offering items in the specified category. |
| categoryAspects.aspects.aspectConstraint.aspectUsage | string | No | The enumeration value returned in this field will indicate if the corresponding aspect is recommended or optional. Note: This field is always returned, even for hard-mandated/required aspects (where aspectRequired : true ). The value returned for required aspects will be RECOMMENDED , but they are a |
| categoryAspects.aspects.aspectConstraint.expectedRequiredByDate | string | No | The expected date after which the aspect will be required. Note: The value returned in this field specifies only an approximate date, which may not reflect the actual date after which the aspect is required. |
| categoryAspects.aspects.aspectConstraint.itemToAspectCardinality | string | No | Indicates whether this aspect can accept single or multiple values for items in the specified category. Note: Up to 30 values can be supplied for aspects that accept multiple values. For implementation help, refer to eBay API documentation |
| categoryAspects.aspects.aspectConstraint.aspectAdvancedDataType | string | No | Indicates additional data type requirements for the aspect. For example, NUMERIC_RANGE indicates that the aspect value must be in numeric range format. Note: Currently only NUMERIC_RANGE is supported. For implementation help, refer to eBay API documentation |
| categoryAspects.aspects.aspectValues | array<AspectValue> | No | A list of valid values for this aspect (for example: Red , Green , and Blue ), along with any constraints on those values. |
| categoryAspects.aspects.aspectValues.localizedValue | string | No | The localized value of this aspect. Note: This value is always localized for the specified marketplace. |
| categoryAspects.aspects.aspectValues.valueConstraints | array<ValueConstraint> | No | Not returned if the value of the localizedValue field can always be selected for this aspect of the specified category. Contains a list of the dependencies that identify when the value of the localizedValue field is available for the current aspect. Each dependency specifies the values of another as |
| categoryAspects.aspects.aspectValues.valueConstraints.applicableForLocalizedAspectName | string | No | The name of the control aspect on which the current aspect value depends. |
| categoryAspects.aspects.aspectValues.valueConstraints.applicableForLocalizedAspectValues | array<string> | No | Contains a list of the values of the control aspect on which this aspect's value depends. When the control aspect has any of the specified values, the current value of the current aspect will also be available. |
| categoryAspects.aspects.localizedAspectName | string | No | The localized name of this aspect (for example: Colour on the eBay UK site). Note: This name is always localized for the specified marketplace. |
| categoryAspects.aspects.relevanceIndicator | RelevanceIndicator | No | The relevance of this aspect. This field is returned if eBay has data on how many searches have been performed for listings in the category using this item aspect. Note: This container is restricted to applications that have been granted permission to access this feature. You must submit an App Chec |
| categoryAspects.aspects.relevanceIndicator.searchCount | integer | No | The number of recent searches (based on 30 days of data) for the aspect. |
