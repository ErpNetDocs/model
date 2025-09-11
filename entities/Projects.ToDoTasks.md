---
uid: Projects.TodoTasks
---
# Projects.TodoTasks Entity

**Namespace:** [Projects](Projects.md)  

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.TodoTasks](Projects.TodoTasks.md)  
  * [Projects.TodoTaskItems](Projects.TodoTaskItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedDateTimeUtc](Projects.TodoTasks.md#completeddatetimeutc) | datetime __nullable__ | Indicates (in UTC) when the task was completed. `Filter(eq;ge;le)` `ReadOnly` 
| [DisplayText](Projects.TodoTasks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DueDate](Projects.TodoTasks.md#duedate) | date __nullable__ | Indicates when the task should be finished. `Filter(eq;ge;le)` 
| [Id](Projects.TodoTasks.md#id) | guid |  
| [Importance](Projects.TodoTasks.md#importance) | [Importance](Projects.TodoTasks.md#importance) | The importance of the task. `Required` `Default("N")` `Filter(eq)` 
| [Name](Projects.TodoTasks.md#name) | string (254) __nullable__ | A brief description of the task. `Filter(like)` 
| [ObjectVersion](Projects.TodoTasks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RemindTime](Projects.TodoTasks.md#remindtime) | datetimeoffset __nullable__ | When to remind the assigned user for the task. 
| [State](Projects.TodoTasks.md#state) | [State](Projects.TodoTasks.md#state) | Indicates the current task state. `Required` `Default("N")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.TodoTasks.md#assignedtouser) | [Users](Systems.Security.Users.md) | The user, to whom the todo is assigned. `Required` `Filter(multi eq)` |
| [OwnerUser](Projects.TodoTasks.md#owneruser) | [Users](Systems.Security.Users.md) | The user, who created the todo and owns it. `Required` `Filter(multi eq)` |
| [SocialGroup](Projects.TodoTasks.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | When not null, indicates that the todo is contained in and managed by the specified social group. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Items | [TodoTaskItems](Projects.TodoTaskItems.md) | List of `TodoTaskItem`(Projects.TodoTaskItems.md) child objects, based on the `Projects.TodoTaskItem.TodoTask`(Projects.TodoTaskItems.md#todotask) back reference 


## Attribute Details

### CompletedDateTimeUtc

Indicates (in UTC) when the task was completed. `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### DueDate

Indicates when the task should be finished. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### Importance

The importance of the task. `Required` `Default("N")` `Filter(eq)`

_Type_: **[Importance](Projects.TodoTasks.md#importance)**  
_Category_: **System**  
Allowed values for the `Importance`(Projects.TodoTasks.md#importance) data attribute  
_Allowed Values (Projects.TodoTasksRepository.Importance Enum Members)_  

| Value | Description |
| ---- | --- |
| Low | Low value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Low' |
| Normal | Normal value. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Normal' |
| High | High value. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'High' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Normal**  

### Name

A brief description of the task. `Filter(like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### RemindTime

When to remind the assigned user for the task.

_Type_: **datetimeoffset __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### State

Indicates the current task state. `Required` `Default("N")` `Filter(eq)`

_Type_: **[State](Projects.TodoTasks.md#state)**  
_Category_: **System**  
Allowed values for the `State`(Projects.TodoTasks.md#state) data attribute  
_Allowed Values (Projects.TodoTasksRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| New | The task is new and its execution is pending. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| InProgress | The task is in progress.. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InProgress' |
| Waiting | The task is pending.. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Waiting' |
| Completed | The task is done.. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Completed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **New**  


## Reference Details

### AssignedToUser

The user, to whom the todo is assigned. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### OwnerUser

The user, who created the todo and owns it. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### SocialGroup

When not null, indicates that the todo is contained in and managed by the specified social group. `Filter(multi eq)`

_Type_: **[Groups](Communities.Social.Groups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification a sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Projects.TodoTasks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.TodoTasks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TodoTasks?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TodoTasks?$top=10>

