---
uid: Applications.Cms.WebSiteLanguages
---
# Applications.Cms.WebSiteLanguages Entity

**Namespace:** [Applications.Cms](Applications.Cms.md)  

Specifies a language, supported by the web site. Entity: Cms_Web_Site_Languages (Obsoleted in version 22.1.6.73)

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Default Visualization
Default Display Text Format:  
_{WebSite.Name}_  
Default Search Members:  
_LanguageCode; WebSite.Name_  
Code Data Member:  
_LanguageCode_  
Name Data Member:  
_WebSite.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Cms.WebSites](Applications.Cms.WebSites.md)  
Aggregate Root:  
[Applications.Cms.WebSites](Applications.Cms.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Cms.WebSiteLanguages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Cms.WebSiteLanguages.md#id) | guid |  
| [IsActive](Applications.Cms.WebSiteLanguages.md#isactive) | boolean | Specifies whether the support for the language is activated and should be published on the web. `Required` `Default(false)` 
| [LanguageCode](Applications.Cms.WebSiteLanguages.md#languagecode) | string (2) | Two letter ISO language code. Sub-tags are currently not supported. `Required` 
| [Notes](Applications.Cms.WebSiteLanguages.md#notes) | string (max) __nullable__ | Notes for this WebSiteLanguage. 
| [ObjectVersion](Applications.Cms.WebSiteLanguages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>WebSite</s>](Applications.Cms.WebSiteLanguages.md#website) | [WebSites](Applications.Cms.WebSites.md) | **OBSOLETE! Do not use!** The web site, for which the language is specified. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner` |


## Attribute Details

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Specifies whether the support for the language is activated and should be published on the web. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LanguageCode

Two letter ISO language code. Sub-tags are currently not supported. `Required`

_Type_: **string (2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this WebSiteLanguage.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### WebSite

**OBSOLETE! Do not use!** The web site, for which the language is specified. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner`

_Type_: **[WebSites](Applications.Cms.WebSites.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
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

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
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
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Applications.Cms.WebSiteLanguages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Cms.WebSiteLanguages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Cms_WebSiteLanguages

Domain API Entity Type: 
Applications_Cms_WebSiteLanguage

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Cms_WebSiteLanguages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Cms_WebSiteLanguages?$top=10>

