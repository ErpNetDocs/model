---
uid: Projects.Procedures.OperationalProcedureExecutions
---
# Projects.Procedures.OperationalProcedureExecutions


A concrete run of a procedure attached to a specific work item (case/task/service doc).

## General
Namespace: [Projects.Procedures](Projects.Procedures.md)  
Repository: Projects.Procedures.OperationalProcedureExecutions  
Base Table: Op_Operational_Procedure_Executions  
Introduced In Version: 26.2.0.99  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {OperationalProcedureId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Procedures.OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md)  
  * [Projects.Procedures.ChecklistExecutionItems](Projects.Procedures.ChecklistExecutionItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedAtUtc](Projects.Procedures.OperationalProcedureExecutions.md#completedatutc) | datetime | When the procedure was completed.`Required` `Filter(eq;ge;le)` `ReadOnly` 
| [StartedAtUtc](Projects.Procedures.OperationalProcedureExecutions.md#startedatutc) | datetime | When the procedure was started.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [Status](Projects.Procedures.OperationalProcedureExecutions.md#status) | [Status](Projects.Procedures.OperationalProcedureExecutions.md#status) | Current status.`Required` `Default(&quot;NEW&quot;)` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [OperationalProcedure](Projects.Procedures.OperationalProcedureExecutions.md#operationalprocedure) | [OperationalProcedures](Projects.Procedures.OperationalProcedures.md) | Which procedure is executed. |
| [SubjectDataObject](Projects.Procedures.OperationalProcedureExecutions.md#subjectdataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object, for which the procedure is executed. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Procedures.OperationalProcedureExecutions.md#id) | guid |  
| [ObjectVersion](Projects.Procedures.OperationalProcedureExecutions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Procedures.OperationalProcedureExecutions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Procedures.OperationalProcedureExecutions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Procedures.OperationalProcedureExecutions.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Procedures.OperationalProcedureExecutions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ChecklistExecutionItems | [ChecklistExecutionItems](Projects.Procedures.ChecklistExecutionItems.md) | List of `ChecklistExecutionItem`(Projects.Procedures.ChecklistExecutionItems.md) child objects, based on the `Projects.Procedures.ChecklistExecutionItem.OperationalProcedure<br />Execution`(Projects.Procedures.ChecklistExecutionItems.md#operationalprocedureexecution) back reference 


## Attribute Details

### CompletedAtUtc

When the procedure was completed.`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StartedAtUtc

When the procedure was started.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Status

Current status.`Required` `Default(&quot;NEW&quot;)` `Filter(multi eq)`

Type: **[Status](Projects.Procedures.OperationalProcedureExecutions.md#status)**  
Category: **System**  
Allowed values for the `Status`(Projects.Procedures.OperationalProcedureExecutions.md#status) data attribute  
Allowed Values (Projects.Procedures.OperationalProcedureExecutionsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| New | New. Stored as 'NEW'. <br /> Database Value: 'NEW' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| InProgress | In Progress. Stored as 'INP'. <br /> Database Value: 'INP' <br /> Model Value: 1 <br /> Domain API Value: 'InProgress' |
| Completed | Completed. Stored as 'CMP'. <br /> Database Value: 'CMP' <br /> Model Value: 2 <br /> Domain API Value: 'Completed' |
| Cancelled | Cancelled. Stored as 'CNC'. <br /> Database Value: 'CNC' <br /> Model Value: 3 <br /> Domain API Value: 'Cancelled' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **New**  
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

### OperationalProcedure

Which procedure is executed.

Type: **[OperationalProcedures](Projects.Procedures.OperationalProcedures.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SubjectDataObject

The object, for which the procedure is executed.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
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

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedureExecutions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Procedures.OperationalProcedureExecutions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Procedures_OperationalProcedureExecutions

Domain API Entity Type: 
Projects_Procedures_OperationalProcedureExecution

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Procedures_OperationalProcedureExecutions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Procedures_OperationalProcedureExecutions?$top=10>

