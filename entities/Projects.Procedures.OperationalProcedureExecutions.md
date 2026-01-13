---
uid: Projects.Procedures.OperationalProcedureExecutions
---
# Projects.Procedures.OperationalProcedureExecutions Entity

**Namespace:** [Projects.Procedures](Projects.Procedures.md)  

A concrete run of a procedure attached to a specific work item (case/task/service doc). Entity: Op_Operational_Procedure_Executions (Introduced in version 26.2.0.99)

## Default Visualization
Default Display Text Format:  
_{Id}: {OperationalProcedureId}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Procedures.OperationalProcedureExecutions](Projects.Procedures.OperationalProcedureExecutions.md)  
  * [Projects.Procedures.ChecklistExecutionItems](Projects.Procedures.ChecklistExecutionItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedAtUtc](Projects.Procedures.OperationalProcedureExecutions.md#completedatutc) | datetime | When the procedure was completed. `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [DisplayText](Projects.Procedures.OperationalProcedureExecutions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Procedures.OperationalProcedureExecutions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Procedures.OperationalProcedureExecutions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Procedures.OperationalProcedureExecutions.md#id) | guid |  
| [ObjectVersion](Projects.Procedures.OperationalProcedureExecutions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartedAtUtc](Projects.Procedures.OperationalProcedureExecutions.md#startedatutc) | datetime | When the procedure was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly` 
| [Status](Projects.Procedures.OperationalProcedureExecutions.md#status) | [Status](Projects.Procedures.OperationalProcedureExecutions.md#status) | Current status. `Required` `Default("NEW")` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [OperationalProcedure](Projects.Procedures.OperationalProcedureExecutions.md#operationalprocedure) | [OperationalProcedures](Projects.Procedures.OperationalProcedures.md) | Which procedure is executed. `Required` `Filter(multi eq)` |
| [SubjectDataObject](Projects.Procedures.OperationalProcedureExecutions.md#subjectdataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) | The object, for which the procedure is executed. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ChecklistExecutionItems | [ChecklistExecutionItems](Projects.Procedures.ChecklistExecutionItems.md) | List of `ChecklistExecutionItem`(Projects.Procedures.ChecklistExecutionItems.md) child objects, based on the `Projects.Procedures.ChecklistExecutionItem.OperationalProcedure<br />Execution`(Projects.Procedures.ChecklistExecutionItems.md#operationalprocedureexecution) back reference 


## Attribute Details

### CompletedAtUtc

When the procedure was completed. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartedAtUtc

When the procedure was started. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Status

Current status. `Required` `Default("NEW")` `Filter(multi eq)`

_Type_: **[Status](Projects.Procedures.OperationalProcedureExecutions.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Projects.Procedures.OperationalProcedureExecutions.md#status) data attribute  
_Allowed Values (Projects.Procedures.OperationalProcedureExecutionsRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New. Stored as 'NEW'. <br /> _Database Value:_ 'NEW' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| InProgress | In Progress. Stored as 'INP'. <br /> _Database Value:_ 'INP' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InProgress' |
| Completed | Completed. Stored as 'CMP'. <br /> _Database Value:_ 'CMP' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Completed' |
| Cancelled | Cancelled. Stored as 'CNC'. <br /> _Database Value:_ 'CNC' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Cancelled' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### OperationalProcedure

Which procedure is executed. `Required` `Filter(multi eq)`

_Type_: **[OperationalProcedures](Projects.Procedures.OperationalProcedures.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SubjectDataObject

The object, for which the procedure is executed. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

