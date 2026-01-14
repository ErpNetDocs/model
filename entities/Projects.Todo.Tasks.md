---
uid: Projects.Todo.Tasks
---
# Projects.Todo.Tasks Entity

**Namespace:** [Projects.Todo](Projects.Todo.md)  

Represents a task, such as a piece of work or personal item, that can be tracked and completed. Entity: Gen_Todo_Tasks (Introduced in version 23.1.1.39)

## Default Visualization
Default Display Text Format:  
_{Title}_  
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
* [Projects.Todo.Tasks](Projects.Todo.Tasks.md)  
  * [Projects.Todo.TaskItems](Projects.Todo.TaskItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Projects.Todo.Tasks.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [CompletedDateTimeUtc](Projects.Todo.Tasks.md#completeddatetimeutc) | datetime __nullable__ | Indicates (in UTC) when the task was completed. `Filter(eq;ge;le)` `ReadOnly` 
| [CreationTimeUtc](Projects.Todo.Tasks.md#creationtimeutc) | datetime | Indicates (in UTC) when the task was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly` `Introduced in version 26.1.4.61` 
| [DisplayText](Projects.Todo.Tasks.md#displaytext) | string |  
| [DueDate](Projects.Todo.Tasks.md#duedate) | date __nullable__ | Indicates when the task should be finished. `Filter(eq;ge;le)` `ORD` 
| [ExternalId](Projects.Todo.Tasks.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Todo.Tasks.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Todo.Tasks.md#id) | guid |  
| [Importance](Projects.Todo.Tasks.md#importance) | [Importance](Projects.Todo.Tasks.md#importance) | The importance of the task. `Required` `Default("N")` `Filter(eq)` 
| [Notes](Projects.Todo.Tasks.md#notes) | string (max) __nullable__ | Notes for this Task. `Introduced in version 23.1.1.48` 
| [ObjectVersion](Projects.Todo.Tasks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RemindTimeUtc](Projects.Todo.Tasks.md#remindtimeutc) | datetime __nullable__ | When to remind the assigned user for the task (in UTC). `Filter(eq;ge;le)` `Introduced in version 23.1.1.51` 
| [State](Projects.Todo.Tasks.md#state) | [State](Projects.Todo.Tasks.md#state) | Indicates the current task state. `Required` `Default("N")` `Filter(multi eq)` 
| [Title](Projects.Todo.Tasks.md#title) | string (254) | A brief description of the task. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.Todo.Tasks.md#assignedtouser) | [Users](Systems.Security.Users.md) | The user, to whom the todo is assigned. `Required` `Filter(multi eq)` |
| [DataObject](Projects.Todo.Tasks.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The object for which this is a to-do item. `Filter(multi eq)` `Introduced in version 25.1.2.60` `FilterableReference` |
| [OwnerUser](Projects.Todo.Tasks.md#owneruser) | [Users](Systems.Security.Users.md) | The user, who created the todo and owns it. `Required` `Filter(multi eq)` |
| [SocialGroup](Projects.Todo.Tasks.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | When not null, indicates that the todo is contained in and managed by the specified social group. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Items | [TaskItems](Projects.Todo.TaskItems.md) | List of `TaskItem`(Projects.Todo.TaskItems.md) child objects, based on the `Projects.Todo.TaskItem.Task`(Projects.Todo.TaskItems.md#task) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CompletedDateTimeUtc

Indicates (in UTC) when the task was completed. `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

Indicates (in UTC) when the task was created. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` `ORD` `ReadOnly` `Introduced in version 26.1.4.61`

_Type_: **datetime**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DisplayText

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DueDate

Indicates when the task should be finished. `Filter(eq;ge;le)` `ORD`

_Type_: **date __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

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
_Show in UI_: **CannotBeShown**  

### Importance

The importance of the task. `Required` `Default("N")` `Filter(eq)`

_Type_: **[Importance](Projects.Todo.Tasks.md#importance)**  
_Category_: **System**  
Allowed values for the `Importance`(Projects.Todo.Tasks.md#importance) data attribute  
_Allowed Values (Projects.Todo.TasksRepository.Importance Enum Members)_  

| Value | Description |
| ---- | --- |
| Low | Low value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Low' |
| Normal | Normal value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Normal' |
| High | High value. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'High' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Normal**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Task. `Introduced in version 23.1.1.48`

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

### RemindTimeUtc

When to remind the assigned user for the task (in UTC). `Filter(eq;ge;le)` `Introduced in version 23.1.1.51`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### State

Indicates the current task state. `Required` `Default("N")` `Filter(multi eq)`

_Type_: **[State](Projects.Todo.Tasks.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Projects.Todo.Tasks.md#state) data attribute  
_Allowed Values (Projects.Todo.TasksRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| InProgress | InProgress value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InProgress' |
| Waiting | Waiting value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Waiting' |
| Completed | Completed value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Completed' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **HiddenByDefault**  

### Title

A brief description of the task. `Required` `Filter(like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AssignedToUser

The user, to whom the todo is assigned. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DataObject

The object for which this is a to-do item. `Filter(multi eq)` `Introduced in version 25.1.2.60` `FilterableReference`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### OwnerUser

The user, who created the todo and owns it. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SocialGroup

When not null, indicates that the todo is contained in and managed by the specified social group. `Filter(multi eq)`

_Type_: **[Groups](Communities.Social.Groups.md) (nullable)**  
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

