---
uid: Projects.Agile.CaseDevelopments
---
# Projects.Agile.CaseDevelopments


Case Development

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.CaseDevelopments  
Base Table: Apm_Case_Developments  
Introduced In Version: 24.1.3.81  
API access:  ReadWrite  

## Visualization
Display Format: {CreationTimeUtc} {ActionDescription} by {CreationUser}  
Search Members: Case.Title  
Name Member: Case.Title  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Agile.Cases](Projects.Agile.Cases.md)  
Aggregate Root:  
[Projects.Agile.Cases](Projects.Agile.Cases.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActionDescription](Projects.Agile.CaseDevelopments.md#actiondescription) | string | Specifies the latest action, dependent on DevelopmentType. 
| [CreationTimeUtc](Projects.Agile.CaseDevelopments.md#creationtimeutc) | datetime | The exact date and time (in UTC) when the development was created[Required] [Default(NowUtc)] [Filter(ge;le)] [ORD] [ReadOnly] 
| [Description](Projects.Agile.CaseDevelopments.md#description) | string (max) __nullable__ | Detailed description of the development.[Filter(like)] 
| [DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype) | [DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype) | Type of the development - Edit, Assignment, Resolve, etc.[Required] [Default(&quot;EDT&quot;)] [Filter(multi eq)] [ReadOnly] 
| [NewSystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) | [SystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) __nullable__ | When the development incurred changing the state of the case, contains the new state.[Filter(multi eq)] [ReadOnly] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.Agile.CaseDevelopments.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | When the development incurred re-assignment, specifies the new user, to which the case is assigned. |
| [Case](Projects.Agile.CaseDevelopments.md#case) | [Cases](Projects.Agile.Cases.md) | The case of the case development |
| [CreationUser](Projects.Agile.CaseDevelopments.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the development. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.CaseDevelopments.md#id) | guid |  
| [ObjectVersion](Projects.Agile.CaseDevelopments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Agile.CaseDevelopments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActionDescription

Specifies the latest action, dependent on DevelopmentType.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the development was created[Required] [Default(NowUtc)] [Filter(ge;le)] [ORD] [ReadOnly]

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Description

Detailed description of the development.[Filter(like)]

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### DevelopmentType

Type of the development - Edit, Assignment, Resolve, etc.[Required] [Default(&quot;EDT&quot;)] [Filter(multi eq)] [ReadOnly]

Type: **[DevelopmentType](Projects.Agile.CaseDevelopments.md#developmenttype)**  
Category: **System**  
Allowed values for the `DevelopmentType`(Projects.Agile.CaseDevelopments.md#developmenttype) data attribute  
Allowed Values (Projects.Agile.CaseDevelopmentsRepository.DevelopmentType Enum Members)  

| Value | Description |
| ---- | --- |
| Edit | Edit. Stored as 'EDT'. <br /> Database Value: 'EDT' <br /> Model Value: 0 <br /> Domain API Value: 'Edit' |
| Assignment | Assignment . Stored as 'ASN'. <br /> Database Value: 'ASN' <br /> Model Value: 1 <br /> Domain API Value: 'Assignment' |
| ChangeState | Change state. Stored as 'STA'. <br /> Database Value: 'STA' <br /> Model Value: 2 <br /> Domain API Value: 'ChangeState' |
| AssignmentH | Assignment. Stored as 'ASH'. <br /> Database Value: 'ASH' <br /> Model Value: 3 <br /> Domain API Value: 'AssignmentH' |
| ChangeStateH | Change state. Stored as 'STH'. <br /> Database Value: 'STH' <br /> Model Value: 4 <br /> Domain API Value: 'ChangeStateH' |
| Create | Create. Stored as 'CRT'. <br /> Database Value: 'CRT' <br /> Model Value: 5 <br /> Domain API Value: 'Create' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Edit**  
Show in UI: **ShownByDefault**  

### NewSystemState

When the development incurred changing the state of the case, contains the new state.[Filter(multi eq)] [ReadOnly]

Type: **[SystemState](Projects.Agile.CaseDevelopments.md#newsystemstate) __nullable__**  
Category: **System**  
Allowed values for the `SystemState`(Projects.Agile.Cases.md#systemstate) data attribute  
Allowed Values (Projects.Agile.CasesRepository.SystemState Enum Members)  

| Value | Description |
| ---- | --- |
| BACKLOG | The case is registered but not yet considered for work.. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'BACKLOG' |
| CONSIDER | The case is under evaluation for possible execution.. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'CONSIDER' |
| READY | The case is approved and ready to be started.. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'READY' |
| INPROGRESS | Work on the case is currently ongoing.. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'INPROGRESS' |
| WAITING | The case is paused, waiting for input or conditions.. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'WAITING' |
| RESOLVED | Work is completed; final review or confirmation may be pending.. Stored as '6'. <br /> Database Value: '6' <br /> Model Value: 5 <br /> Domain API Value: 'RESOLVED' |
| CLOSED | The case is finalized and officially closed.. Stored as '7'. <br /> Database Value: '7' <br /> Model Value: 6 <br /> Domain API Value: 'CLOSED' |

Supported Filters: **Equals, EqualsIn**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### AssignedToUser

When the development incurred re-assignment, specifies the new user, to which the case is assigned.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Case

The case of the case development

Type: **[Cases](Projects.Agile.Cases.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### CreationUser

The user, who created the development.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Projects.Agile.CaseDevelopments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.CaseDevelopments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_CaseDevelopments

Domain API Entity Type: 
Projects_Agile_CaseDevelopment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_CaseDevelopments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_CaseDevelopments?$top=10>

