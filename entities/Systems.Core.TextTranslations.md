---
uid: Systems.Core.TextTranslations
---
# Systems.Core.TextTranslations Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Obsolete. Not used. Entity: Gen_Text_Translations

## Default Visualization
Default Display Text Format:  
_{ColumnName}_  
Default Search Members:  
_ColumnName_  
Name Data Member:  
_ColumnName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.TextTranslations](Systems.Core.TextTranslations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ColumnName](Systems.Core.TextTranslations.md#columnname) | string (128) | Obsolete. Not used. `Required` `Filter(eq)` 
| [DisplayText](Systems.Core.TextTranslations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Core.TextTranslations.md#id) | guid |  
| [Language](Systems.Core.TextTranslations.md#language) | string (50) | Obsolete. Not used. `Required` `Filter(eq)` 
| [ObjectVersion](Systems.Core.TextTranslations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RowId](Systems.Core.TextTranslations.md#rowid) | guid | Obsolete. Not used. `Required` `Filter(multi eq)` 
| [TableName](Systems.Core.TextTranslations.md#tablename) | string (128) | Obsolete. Not used. `Required` `Filter(eq)` `ORD` `ReadOnly` 
| [TranslatedText](Systems.Core.TextTranslations.md#translatedtext) | string (254) __nullable__ | Obsolete. Not used. `Filter(eq)` 


## Attribute Details

### ColumnName

Obsolete. Not used. `Required` `Filter(eq)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Language

Obsolete. Not used. `Required` `Filter(eq)`

_Type_: **string (50)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### RowId

Obsolete. Not used. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### TableName

Obsolete. Not used. `Required` `Filter(eq)` `ORD` `ReadOnly`

_Type_: **string (128)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  

### TranslatedText

Obsolete. Not used. `Filter(eq)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  



## Business Rules

[!list limit=1000 erp.entity=Systems.Core.TextTranslations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.TextTranslations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_TextTranslations?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_TextTranslations?$top=10>

