---
uid: Systems.Config.Translations
---
# Systems.Config.Translations


Contains user-defined translations for non-english languages of the user interface and program messages.

## General
Namespace: [Systems.Config](Systems.Config.md)  
Repository: Systems.Config.Translations  
Base Table: Sys_Translations  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.Translations  
New name: Systems.Config.Translations  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ApplicationName}  
Search Members: ApplicationName  
Name Member: ApplicationName  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.Translations](Systems.Config.Translations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Systems.Config.Translations.md#active) | boolean | True when the translation is verified and activated. 
| [ApplicationName](Systems.Config.Translations.md#applicationname) | string (50) __nullable__ | The application, containing the resource. For base resource types (T,C,H), this is NULL 
| [CreationTime](Systems.Config.Translations.md#creationtime) | datetime | Timestamp when the translation was first created 
| [Language](Systems.Config.Translations.md#language) | string (8) | The code of the language by the ISO639-1 two letter language coding: "en"=English, "bg"=Bulgarian. 
| [ResourceId](Systems.Config.Translations.md#resourceid) | string (800) | The unique identifier of the translated resource. Should use ASCII/English chars only. Shorter strings are suggested. Depending on Text_Type: T:TableName; C:ColumnName; H:TableName.ColumnName; E,M,S: Application specific code 
| [ResourceType](Systems.Config.Translations.md#resourcetype) | [ResourceType](Systems.Config.Translations.md#resourcetype) | T=Table (entity) Name; C=Column Name; H=Column Hint; R=Meta Resource; E=Error; M=Message; S=Other application specific String 
| [TranslationField](Systems.Config.Translations.md#translationfield) | string (max) | The translated text 
| [UpdateTime](Systems.Config.Translations.md#updatetime) | datetime | When the translation was last updated 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Config.Translations.md#id) | guid |  
| [ObjectVersion](Systems.Config.Translations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Config.Translations.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.Translations.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Config.Translations.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.Translations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Active

True when the translation is verified and activated.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( Not( IsNullOrEmpty( obj.TranslationField)), True, obj.Active)`
### ApplicationName

The application, containing the resource. For base resource types (T,C,H), this is NULL

Type: **string (50) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### CreationTime

Timestamp when the translation was first created

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Language

The code of the language by the ISO639-1 two letter language coding: "en"=English, "bg"=Bulgarian.

Type: **string (8)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **8**  
Default Value: **en**  
Show in UI: **ShownByDefault**  

### ResourceId

The unique identifier of the translated resource. Should use ASCII/English chars only. Shorter strings are suggested. Depending on Text_Type: T:TableName; C:ColumnName; H:TableName.ColumnName; E,M,S: Application specific code

Type: **string (800)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **800**  
Show in UI: **ShownByDefault**  

### ResourceType

T=Table (entity) Name; C=Column Name; H=Column Hint; R=Meta Resource; E=Error; M=Message; S=Other application specific String

Type: **[ResourceType](Systems.Config.Translations.md#resourcetype)**  
Category: **System**  
Allowed values for the `ResourceType`(Systems.Config.Translations.md#resourcetype) data attribute  
Allowed Values (Systems.Config.TranslationsRepository.ResourceType Enum Members)  

| Value | Description |
| ---- | --- |
| TableName | TableName value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 0 <br /> Domain API Value: 'TableName' |
| ColumnName | ColumnName value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'ColumnName' |
| ColumnHint | ColumnHint value. Stored as 'H'. <br /> Database Value: 'H' <br /> Model Value: 2 <br /> Domain API Value: 'ColumnHint' |
| MetaResource | MetaResource value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 3 <br /> Domain API Value: 'MetaResource' |
| ErrorMessage | ErrorMessage value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 4 <br /> Domain API Value: 'ErrorMessage' |
| Message | Message value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 5 <br /> Domain API Value: 'Message' |
| OtherApplicationSpecific | OtherApplicationSpecific value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 6 <br /> Domain API Value: 'OtherApplicationSpecific' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **OtherApplicationSpecific**  
Show in UI: **ShownByDefault**  

### TranslationField

The translated text

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### UpdateTime

When the translation was last updated

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
Show in UI: **CannotBeShown**  

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

[!list limit=1000 erp.entity=Systems.Config.Translations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Config.Translations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Config_Translations

Domain API Entity Type: 
Systems_Config_Translation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Config_Translations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Config_Translations?$top=10>

