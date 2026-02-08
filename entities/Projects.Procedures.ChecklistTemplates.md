---
uid: Projects.Procedures.ChecklistTemplates
---
# Projects.Procedures.ChecklistTemplates


Reusable checklist definition (structure before execution).

## General
Namespace: [Projects.Procedures](Projects.Procedures.md)  
Repository: Projects.Procedures.ChecklistTemplates  
Base Table: Op_Checklist_Templates  
Introduced In Version: 26.2.1.0  
API access:  ReadWrite  

## Visualization
Display Format: {Code}  
Search Members: Code  
Code Member: Code  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Procedures.ChecklistTemplates](Projects.Procedures.ChecklistTemplates.md)  
  * [Projects.Procedures.ChecklistTemplateItems](Projects.Procedures.ChecklistTemplateItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Projects.Procedures.ChecklistTemplates.md#code) | string (32) | Short code (optional).`Required` `Filter(eq;like)` 
| [Description](Projects.Procedures.ChecklistTemplates.md#description) | string (max) __nullable__ | Purpose/usage notes.`Filter(like)` 
| [Status](Projects.Procedures.ChecklistTemplates.md#status) | [Status](Projects.Procedures.ChecklistTemplates.md#status) | State (Draft/Active/Obsolete).`Required` `Default(&quot;DRF&quot;)` `Filter(eq)` 
| [Title](Projects.Procedures.ChecklistTemplates.md#title) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Template name (multilanguage).`Required` `Filter(like)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Procedures.ChecklistTemplates.md#id) | guid |  
| [ObjectVersion](Projects.Procedures.ChecklistTemplates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Procedures.ChecklistTemplates.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Procedures.ChecklistTemplates.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Procedures.ChecklistTemplates.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Procedures.ChecklistTemplates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Items | [ChecklistTemplateItems](Projects.Procedures.ChecklistTemplateItems.md) | List of `ChecklistTemplateItem`(Projects.Procedures.ChecklistTemplateItems.md) child objects, based on the `Projects.Procedures.ChecklistTemplateItem.ChecklistTemplate`(Projects.Procedures.ChecklistTemplateItems.md#checklisttemplate) back reference 


## Attribute Details

### Code

Short code (optional).`Required` `Filter(eq;like)`

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Description

Purpose/usage notes.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Status

State (Draft/Active/Obsolete).`Required` `Default(&quot;DRF&quot;)` `Filter(eq)`

Type: **[Status](Projects.Procedures.ChecklistTemplates.md#status)**  
Category: **System**  
Allowed values for the `Status`(Projects.Procedures.ChecklistTemplates.md#status) data attribute  
Allowed Values (Projects.Procedures.ChecklistTemplatesRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| Draft | Draft. Stored as 'DRF'. <br /> Database Value: 'DRF' <br /> Model Value: 0 <br /> Domain API Value: 'Draft' |
| Active | Active. Stored as 'ACT'. <br /> Database Value: 'ACT' <br /> Model Value: 1 <br /> Domain API Value: 'Active' |
| Obsolete | Obsolete. Stored as 'OBS'. <br /> Database Value: 'OBS' <br /> Model Value: 2 <br /> Domain API Value: 'Obsolete' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Draft**  
Show in UI: **ShownByDefault**  

### Title

Template name (multilanguage).`Required` `Filter(like)`

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
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

[!list limit=1000 erp.entity=Projects.Procedures.ChecklistTemplates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Procedures.ChecklistTemplates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Procedures_ChecklistTemplates

Domain API Entity Type: 
Projects_Procedures_ChecklistTemplate

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Procedures_ChecklistTemplates?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Procedures_ChecklistTemplates?$top=10>

