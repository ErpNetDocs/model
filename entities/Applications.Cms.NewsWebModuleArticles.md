---
uid: Applications.Cms.NewsWebModuleArticles
---
# Applications.Cms.NewsWebModuleArticles


Represents an article in a news web module.

## General
Namespace: [Applications.Cms](Applications.Cms.md)  
Repository: Applications.Cms.NewsWebModuleArticles  
Base Table: Cms_News_Web_Module_Articles  
API access:  ReadWrite  

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Visualization
Display Format: {LanguageCode}  
Search Members: LanguageCode  
Code Member: LanguageCode  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Cms.NewsWebModuleArticles](Applications.Cms.NewsWebModuleArticles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ArticleTextHtml](Applications.Cms.NewsWebModuleArticles.md#articletexthtml) | string (max) __nullable__ | The actual article text, stored as Html. Only the <BODY> of the Html is stored. The language of the text is specified in Language Code. 
| [IsPublished](Applications.Cms.NewsWebModuleArticles.md#ispublished) | boolean | Specifies whether the article is published for display on web.`Required` `Default(false)` 
| [LanguageCode](Applications.Cms.NewsWebModuleArticles.md#languagecode) | string (8) | The language code of the article text.`Required` 
| [PublishDate](Applications.Cms.NewsWebModuleArticles.md#publishdate) | datetime | The date and time when the news article should appear to be published.`Required` `Default(Now)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>AuthorPublicUser</s>](Applications.Cms.NewsWebModuleArticles.md#authorpublicuser) | [PublicUsers](Systems.External.PublicUsers.md) | **OBSOLETE! Do not use!** The author of the news article. |
| [<s>NewsWebModule</s>](Applications.Cms.NewsWebModuleArticles.md#newswebmodule) | [NewsWebModules](Applications.Cms.NewsWebModules.md) | **OBSOLETE! Do not use!** The News Web Module, to which the current article is added. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Cms.NewsWebModuleArticles.md#id) | guid |  
| [ObjectVersion](Applications.Cms.NewsWebModuleArticles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Cms.NewsWebModuleArticles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Cms.NewsWebModuleArticles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Cms.NewsWebModuleArticles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Cms.NewsWebModuleArticles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ArticleTextHtml

The actual article text, stored as Html. Only the <BODY> of the Html is stored. The language of the text is specified in Language Code.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### IsPublished

Specifies whether the article is published for display on web.`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LanguageCode

The language code of the article text.`Required`

Type: **string (8)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **8**  
Show in UI: **ShownByDefault**  

### PublishDate

The date and time when the news article should appear to be published.`Required` `Default(Now)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### AuthorPublicUser

**OBSOLETE! Do not use!** The author of the news article.

Type: **[PublicUsers](Systems.External.PublicUsers.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### NewsWebModule

**OBSOLETE! Do not use!** The News Web Module, to which the current article is added.

Type: **[NewsWebModules](Applications.Cms.NewsWebModules.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Applications.Cms.NewsWebModuleArticles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Cms.NewsWebModuleArticles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Cms_NewsWebModuleArticles

Domain API Entity Type: 
Applications_Cms_NewsWebModuleArticle

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Cms_NewsWebModuleArticles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Cms_NewsWebModuleArticles?$top=10>

