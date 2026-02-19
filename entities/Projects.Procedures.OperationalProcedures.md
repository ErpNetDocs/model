---
uid: Projects.Procedures.OperationalProcedures
---
# Projects.Procedures.OperationalProcedures


Master record for an operational procedure (“how work is done”).

## General
Namespace: [Projects.Procedures](Projects.Procedures.md)  
Repository: Projects.Procedures.OperationalProcedures  
Base Table: Op_Operational_Procedures  
Introduced In Version: 26.2.0.99  
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
* [Projects.Procedures.OperationalProcedures](Projects.Procedures.OperationalProcedures.md)  
  * [Projects.Procedures.OperationalProcedureChecklistTemplates](Projects.Procedures.OperationalProcedureChecklistTemplates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Projects.Procedures.OperationalProcedures.md#code) | string (32) | Short unique code for search/reference.`Required` `Filter(eq;like)` `ORD` `ReadOnly` 
| [ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat) | [ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat) | Storage format of the content.`Required` `Default(&quot;MKD&quot;)` `Filter(eq)` 
| [CreationTimeUtc](Projects.Procedures.OperationalProcedures.md#creationtimeutc) | datetime | The exact date and time (in UTC) when the procedure was created.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [EntityType](Projects.Procedures.OperationalProcedures.md#entitytype) | string (128) __nullable__ | Name of entity to which the procedure applies`Filter(eq)` 
| [LastUpdateTimeUtc](Projects.Procedures.OperationalProcedures.md#lastupdatetimeutc) | datetime | The exact date and time (in UTC) when the procedure was last updated.`Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Notes](Projects.Procedures.OperationalProcedures.md#notes) | string (max) __nullable__ | Notes for the procedure.`Filter(like)` 
| [ProcedureContent](Projects.Procedures.OperationalProcedures.md#procedurecontent) | string (max) __nullable__ | The content of the procedure.`Filter(like)` 
| [Status](Projects.Procedures.OperationalProcedures.md#status) | [Status](Projects.Procedures.OperationalProcedures.md#status) | Lifecycle state (Draft/Active/Obsolete).`Required` `Default(&quot;DRF&quot;)` `Filter(multi eq)` 
| [Title](Projects.Procedures.OperationalProcedures.md#title) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Procedure name.`Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Projects.Procedures.OperationalProcedures.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the user permissions for this Operational Procedure. |
| [OwnerRole](Projects.Procedures.OperationalProcedures.md#ownerrole) | [Roles](Systems.Security.Roles.md) (nullable) | Responsible role (content owner). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Procedures.OperationalProcedures.md#id) | guid |  
| [ObjectVersion](Projects.Procedures.OperationalProcedures.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Procedures.OperationalProcedures.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Procedures.OperationalProcedures.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Procedures.OperationalProcedures.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Procedures.OperationalProcedures.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ChecklistTemplates | [OperationalProcedureChecklistTemplates](Projects.Procedures.OperationalProcedureChecklistTemplates.md) | List of `OperationalProcedure<br />ChecklistTemplate`(Projects.Procedures.OperationalProcedure<br />ChecklistTemplates.md) child objects, based on the `Projects.Procedures.OperationalProcedure<br />ChecklistTemplate.OperationalProcedure`(Projects.Procedures.OperationalProcedure<br />ChecklistTemplates.md#operationalprocedure) back reference 


## Attribute Details

### Code

Short unique code for search/reference.`Required` `Filter(eq;like)` `ORD` `ReadOnly`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetCode( )`

### ContentFormat

Storage format of the content.`Required` `Default(&quot;MKD&quot;)` `Filter(eq)`

Type: **[ContentFormat](Projects.Procedures.OperationalProcedures.md#contentformat)**  
Category: **System**  
Allowed values for the `ContentFormat`(Projects.Procedures.OperationalProcedures.md#contentformat) data attribute  
Allowed Values (Projects.Procedures.OperationalProceduresRepository.ContentFormat Enum Members)  

| Value | Description |
| ---- | --- |
| MarkDown | MarkDown. Stored as 'MKD'. <br /> Database Value: 'MKD' <br /> Model Value: 0 <br /> Domain API Value: 'MarkDown' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **MarkDown**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the procedure was created.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### EntityType

Name of entity to which the procedure applies`Filter(eq)`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### LastUpdateTimeUtc

The exact date and time (in UTC) when the procedure was last updated.`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`DateTime.UtcNow`

### Notes

Notes for the procedure.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProcedureContent

The content of the procedure.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Status

Lifecycle state (Draft/Active/Obsolete).`Required` `Default(&quot;DRF&quot;)` `Filter(multi eq)`

Type: **[Status](Projects.Procedures.OperationalProcedures.md#status)**  
Category: **System**  
Allowed values for the `Status`(Projects.Procedures.OperationalProcedures.md#status) data attribute  
Allowed Values (Projects.Procedures.OperationalProceduresRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| DRAFT | Draft. Stored as 'DRF'. <br /> Database Value: 'DRF' <br /> Model Value: 0 <br /> Domain API Value: 'DRAFT' |
| ACTIVE | Active. Stored as 'ACT'. <br /> Database Value: 'ACT' <br /> Model Value: 1 <br /> Domain API Value: 'ACTIVE' |
| OBSOLETE | Obsolete. Stored as 'OBS'. <br /> Database Value: 'OBS' <br /> Model Value: 2 <br /> Domain API Value: 'OBSOLETE' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **DRAFT**  
Show in UI: **ShownByDefault**  

### Title

Procedure name.`Required` `Filter(like)`

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


## Reference Details

### AccessKey

The access key, containing the user permissions for this Operational Procedure.

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### OwnerRole

Responsible role (content owner).

Type: **[Roles](Systems.Security.Roles.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedures erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedures erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Procedures_OperationalProcedures

Domain API Entity Type: 
Projects_Procedures_OperationalProcedure

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Procedures_OperationalProcedures?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Procedures_OperationalProcedures?$top=10>

