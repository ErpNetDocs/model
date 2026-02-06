---
uid: Projects.Todo.Tasks
---
# Projects.Todo.Tasks


Represents a task, such as a piece of work or personal item, that can be tracked and completed.

## General
Namespace: [Projects.Todo](Projects.Todo.md)  
Repository: Projects.Todo.Tasks  
Base Table: Gen_Todo_Tasks  
Introduced In Version: 23.1.1.39  
API access:  ReadWrite  

## Visualization
Display Format: {Title}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Todo.Tasks](Projects.Todo.Tasks.md)  
  * [Projects.Todo.TaskItems](Projects.Todo.TaskItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedDateTimeUtc](Projects.Todo.Tasks.md#completeddatetimeutc) | datetime __nullable__ | Indicates (in UTC) when the task was completed. 
| [CreationTimeUtc](Projects.Todo.Tasks.md#creationtimeutc) | datetime | Indicates (in UTC) when the task was created. 
| [DueDate](Projects.Todo.Tasks.md#duedate) | date __nullable__ | Indicates when the task should be finished. 
| [Importance](Projects.Todo.Tasks.md#importance) | [Importance](Projects.Todo.Tasks.md#importance) | The importance of the task. 
| [Notes](Projects.Todo.Tasks.md#notes) | string (max) __nullable__ | Notes for this Task. `Introduced in version 23.1.1.48` 
| [RemindTimeUtc](Projects.Todo.Tasks.md#remindtimeutc) | datetime __nullable__ | When to remind the assigned user for the task (in UTC). 
| [State](Projects.Todo.Tasks.md#state) | [State](Projects.Todo.Tasks.md#state) | Indicates the current task state. 
| [Title](Projects.Todo.Tasks.md#title) | string (254) | A brief description of the task. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.Todo.Tasks.md#assignedtouser) | [Users](Systems.Security.Users.md) | The user, to whom the todo is assigned. |
| [DataObject](Projects.Todo.Tasks.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The object for which this is a to-do item. |
| [OwnerUser](Projects.Todo.Tasks.md#owneruser) | [Users](Systems.Security.Users.md) | The user, who created the todo and owns it. |
| [SocialGroup](Projects.Todo.Tasks.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | When not null, indicates that the todo is contained in and managed by the specified social group. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Todo.Tasks.md#id) | guid |  
| [ObjectVersion](Projects.Todo.Tasks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Todo.Tasks.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Todo.Tasks.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Todo.Tasks.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Todo.Tasks.md#displaytext) | string |  

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Items | [TaskItems](Projects.Todo.TaskItems.md) | List of `TaskItem`(Projects.Todo.TaskItems.md) child objects, based on the `Projects.Todo.TaskItem.Task`(Projects.Todo.TaskItems.md#task) back reference 


## Attribute Details

### CompletedDateTimeUtc

Indicates (in UTC) when the task was completed.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

Indicates (in UTC) when the task was created.

Type: **datetime**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### DueDate

Indicates when the task should be finished.

Type: **date __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Importance

The importance of the task.

Type: **[Importance](Projects.Todo.Tasks.md#importance)**  
Category: **System**  
Allowed values for the `Importance`(Projects.Todo.Tasks.md#importance) data attribute  
Allowed Values (Projects.Todo.TasksRepository.Importance Enum Members)  

| Value | Description |
| ---- | --- |
| Low | Low value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 0 <br /> Domain API Value: 'Low' |
| Normal | Normal value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 1 <br /> Domain API Value: 'Normal' |
| High | High value. Stored as 'H'. <br /> Database Value: 'H' <br /> Model Value: 2 <br /> Domain API Value: 'High' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Normal**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Task. `Introduced in version 23.1.1.48`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RemindTimeUtc

When to remind the assigned user for the task (in UTC).

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### State

Indicates the current task state.

Type: **[State](Projects.Todo.Tasks.md#state)**  
Category: **System**  
Allowed values for the `State`(Projects.Todo.Tasks.md#state) data attribute  
Allowed Values (Projects.Todo.TasksRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| InProgress | InProgress value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'InProgress' |
| Waiting | Waiting value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 2 <br /> Domain API Value: 'Waiting' |
| Completed | Completed value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 3 <br /> Domain API Value: 'Completed' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **New**  
Show in UI: **HiddenByDefault**  

### Title

A brief description of the task.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### AssignedToUser

The user, to whom the todo is assigned.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DataObject

The object for which this is a to-do item.

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### OwnerUser

The user, who created the todo and owns it.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SocialGroup

When not null, indicates that the todo is contained in and managed by the specified social group.

Type: **[Groups](Communities.Social.Groups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Todo.Tasks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Todo.Tasks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Todo_Tasks

Domain API Entity Type: 
Projects_Todo_Task

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Todo_Tasks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Todo_Tasks?$top=10>

