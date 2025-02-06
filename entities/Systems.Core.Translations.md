---
uid: Systems.Core.Translations
---
# Systems.Core.Translations Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains user-defined translations for non-english languages of the user interface and program messages. Entity: Sys_Translations
## Renamed
**New name:** [Systems.Config.Translations](Systems.Config.Translations.md)  



## Default Visualization
Default Display Text Format:  
_{ApplicationName}_  
Default Search Members:  
_ApplicationName_  
Name Data Member:  
_ApplicationName_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.Translations](Systems.Core.Translations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Systems.Core.Translations.md#active) | boolean | True when the translation is verified and activated. `Required` `Default(true)` `Filter(eq)` 
| [ApplicationName](Systems.Core.Translations.md#applicationname) | string (50) __nullable__ | The application, containing the resource. For base resource types (T,C,H), this is null. `Filter(eq)` `ORD` 
| [CreationTime](Systems.Core.Translations.md#creationtime) | datetime | Timestamp when the translation was first created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Systems.Core.Translations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Core.Translations.md#id) | guid |  
| [Language](Systems.Core.Translations.md#language) | string (8) | The code of the language or language-culture pair. Standard Windows codes are used. English="en"; US English = "en-us". `Required` `Default("en")` `Filter(eq)` 
| [ObjectVersion](Systems.Core.Translations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ResourceId](Systems.Core.Translations.md#resourceid) | string (800) | The unique identifier of the translated resource. Should use ASCII/English chars only. Shorter strings are suggested. Depending on Text_Type: T:TableName; C:ColumnName; H:TableName.ColumnName; E,M,S: Application specific code. `Required` `Filter(eq;like)` 
| [ResourceType](Systems.Core.Translations.md#resourcetype) | [ResourceType](Systems.Core.Translations.md#resourcetype) | T=Table (entity) Name; C=Column Name; H=Column Hint; R=Meta Resource; E=Error; M=Message; S=Other application specific String. `Required` `Default("S")` `Filter(eq)` 
| [TranslationField](Systems.Core.Translations.md#translationfield) | string (max) | The translated text. `Required` 
| [UpdateTime](Systems.Core.Translations.md#updatetime) | datetime | When the translation was last updated. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly` 


## Attribute Details

### Active

True when the translation is verified and activated. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( Not( IsNullOrEmpty( obj.TranslationField)), True, obj.Active)`
### ApplicationName

The application, containing the resource. For base resource types (T,C,H), this is null. `Filter(eq)` `ORD`

_Type_: **string (50) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### CreationTime

Timestamp when the translation was first created. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Language

The code of the language or language-culture pair. Standard Windows codes are used. English="en"; US English = "en-us". `Required` `Default("en")` `Filter(eq)`

_Type_: **string (8)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **8**  
_Default Value_: **en**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ResourceId

The unique identifier of the translated resource. Should use ASCII/English chars only. Shorter strings are suggested. Depending on Text_Type: T:TableName; C:ColumnName; H:TableName.ColumnName; E,M,S: Application specific code. `Required` `Filter(eq;like)`

_Type_: **string (800)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **800**  
_Show in UI_: **ShownByDefault**  

### ResourceType

T=Table (entity) Name; C=Column Name; H=Column Hint; R=Meta Resource; E=Error; M=Message; S=Other application specific String. `Required` `Default("S")` `Filter(eq)`

_Type_: **[ResourceType](Systems.Core.Translations.md#resourcetype)**  
_Category_: **System**  
Allowed values for the `ResourceType`(Systems.Core.Translations.md#resourcetype) data attribute  
_Allowed Values (Systems.Core.TranslationsRepository.ResourceType Enum Members)_  

| Value | Description |
| ---- | --- |
| TableName | TableName value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'TableName' |
| ColumnName | ColumnName value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ColumnName' |
| ColumnHint | ColumnHint value. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ColumnHint' |
| MetaResource | MetaResource value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'MetaResource' |
| ErrorMessage | ErrorMessage value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'ErrorMessage' |
| Message | Message value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Message' |
| OtherApplicationSpecific | OtherApplicationSpecific value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'OtherApplicationSpecific' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **OtherApplicationSpecific**  
_Show in UI_: **ShownByDefault**  

### TranslationField

The translated text. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### UpdateTime

When the translation was last updated. `Required` `Default(Now)` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  


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


### CreateNotification

Creates a notification and sends a real time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Core.Translations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.Translations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_Translations?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_Translations?$top=10>

