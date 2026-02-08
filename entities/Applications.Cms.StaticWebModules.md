---
uid: Applications.Cms.StaticWebModules
---
# Applications.Cms.StaticWebModules


A web module, which contains one web page with static text.

## General
Namespace: [Applications.Cms](Applications.Cms.md)  
Repository: Applications.Cms.StaticWebModules  
Inherited From: [Applications.Cms.WebModules](Applications.Cms.WebModules.md)  
Base Table: Cms_Static_Web_Modules  
API access:  ReadWrite  

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Visualization
Display Format: {Name}  
Search Members: LanguageCode; Name  
Code Member: LanguageCode  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Cms.WebSites](Applications.Cms.WebSites.md)  
Aggregate Root:  
[Applications.Cms.WebSites](Applications.Cms.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContentHtml](Applications.Cms.StaticWebModules.md#contenthtml) | string (max) __nullable__ | The actual html content of the pade. Only the <BODY> of the html is stored. 
| [IsPublished](Applications.Cms.StaticWebModules.md#ispublished) | boolean | Specifies whether the module is published and will be showed in the web site. `Required` `Default(false)` `Filter(eq)` (Inherited from [WebModules](Applications.Cms.WebModules.md)) 
| [LanguageCode](Applications.Cms.StaticWebModules.md#languagecode) | string (7) | The language code of the content.`Required` `Default(&quot;EN&quot;)` 
| [LocalUrl](Applications.Cms.StaticWebModules.md#localurl) | string (128) __nullable__ | The local Module Url. The full Url of a module is formed based on the sites Base Url, the local Urls of all parent modules and the module Local Url. Null means that the web Module is the default web module within the parent path. `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md)) 
| [ModulePicture](Applications.Cms.StaticWebModules.md#modulepicture) | byte[] __nullable__ | Default picture. Used for picture links, small module icons, etc. PNG format is suggested. (Inherited from [WebModules](Applications.Cms.WebModules.md)) 
| [ModuleType](Applications.Cms.StaticWebModules.md#moduletype) | [ModuleType](Applications.Cms.StaticWebModules.md#moduletype) | Specifies the content handler. The content handler is responsible for generating the actual web page content. Module Types include Category, Static, News, Product, etc. `Required` `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md)) 
| [Name](Applications.Cms.StaticWebModules.md#name) | string (512) | Multilanguage Module name. This is used as a title when displaying the web Module. `Required` `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md)) 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>Parent</s>](Applications.Cms.StaticWebModules.md#parent) | [WebModules](Applications.Cms.WebModules.md) (nullable) | **OBSOLETE! Do not use!** The parent web Module. It can only be a module with Module Type = Category. Null means that the web Module is root web Module. `Obsolete` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` (Inherited from [WebModules](Applications.Cms.WebModules.md)) |
| [<s>WebSite</s>](Applications.Cms.StaticWebModules.md#website) | [WebSites](Applications.Cms.WebSites.md) | **OBSOLETE! Do not use!** The web site to which the module belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner` (Inherited from [WebModules](Applications.Cms.WebModules.md)) |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Cms.StaticWebModules.md#id) | guid |  
| [ObjectVersion](Applications.Cms.StaticWebModules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Cms.StaticWebModules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ContentHtml

The actual html content of the pade. Only the <BODY> of the html is stored.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### IsPublished

Specifies whether the module is published and will be showed in the web site. `Required` `Default(false)` `Filter(eq)` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LanguageCode

The language code of the content.`Required` `Default(&quot;EN&quot;)`

Type: **string (7)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **7**  
Default Value: **EN**  
Show in UI: **ShownByDefault**  

### LocalUrl

The local Module Url. The full Url of a module is formed based on the sites Base Url, the local Urls of all parent modules and the module Local Url. Null means that the web Module is the default web module within the parent path. `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### ModulePicture

Default picture. Used for picture links, small module icons, etc. PNG format is suggested. (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ModuleType

Specifies the content handler. The content handler is responsible for generating the actual web page content. Module Types include Category, Static, News, Product, etc. `Required` `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **[ModuleType](Applications.Cms.StaticWebModules.md#moduletype)**  
Category: **System**  
Allowed values for the ModuleType data attribute  
Allowed Values (Applications.Cms.WebModulesRepository.ModuleType Enum Members)  

| Value | Description |
| ---- | --- |
| CategoryPage | CategoryPage value. Stored as 'CAT'. <br /> Database Value: 'CAT' <br /> Model Value: 0 <br /> Domain API Value: 'CategoryPage' |
| Static | Static value. Stored as 'STA'. <br /> Database Value: 'STA' <br /> Model Value: 1 <br /> Domain API Value: 'Static' |
| News | News value. Stored as 'NEW'. <br /> Database Value: 'NEW' <br /> Model Value: 2 <br /> Domain API Value: 'News' |

Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

Multilanguage Module name. This is used as a title when displaying the web Module. `Required` `Filter(like)` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **string (512)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **512**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Parent

**OBSOLETE! Do not use!** The parent web Module. It can only be a module with Module Type = Category. Null means that the web Module is root web Module. `Obsolete` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **[WebModules](Applications.Cms.WebModules.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WebSite

**OBSOLETE! Do not use!** The web site to which the module belongs. `Obsolete` `Required` `Filter(multi eq)` `Obsoleted in version 26.2.1.2` `Obsolete` `Owner` (Inherited from [WebModules](Applications.Cms.WebModules.md))

Type: **[WebSites](Applications.Cms.WebSites.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Applications.Cms.StaticWebModules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Cms.StaticWebModules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Cms_StaticWebModules

Domain API Entity Type: 
Applications_Cms_StaticWebModule

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Cms_StaticWebModules?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Cms_StaticWebModules?$top=10>

