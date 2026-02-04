---
uid: Projects.Todo.TaskItems
---
# Projects.Todo.TaskItems


A sub-item of a "to do" task.

## General
Namespace: [Projects.Todo](Projects.Todo.md)  
Repository: Projects.Todo.TaskItems  
Base Table: Gen_Todo_Task_Items  
Introduced In Version: 23.1.1.39  
API access:  ReadWrite  

## Visualization
Display Format: {Task}  
Search Members: Task  
Name Member: Task  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Todo.Tasks](Projects.Todo.Tasks.md)  
Aggregate Root:  
[Projects.Todo.Tasks](Projects.Todo.Tasks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedDateTimeUtc](Projects.Todo.TaskItems.md#completeddatetimeutc) | datetime __nullable__ | Indicates (in UTC) when the task item was completed. 
| [CreatedDateTimeUtc](Projects.Todo.TaskItems.md#createddatetimeutc) | datetime | Indicates (in UTC) when the task item was created. 
| [IsCompleted](Projects.Todo.TaskItems.md#iscompleted) | boolean | Indicates whether the task item is completed. 
| [Notes](Projects.Todo.TaskItems.md#notes) | string (max) __nullable__ | Notes for this TaskItem. `Introduced in version 23.1.1.48` 
| [Title](Projects.Todo.TaskItems.md#title) | string (254) | A brief description of the task item. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Task](Projects.Todo.TaskItems.md#task) | [Tasks](Projects.Todo.Tasks.md) | The task to which this item is part of. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Todo.TaskItems.md#id) | guid |  
| [ObjectVersion](Projects.Todo.TaskItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Todo.TaskItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CompletedDateTimeUtc

Indicates (in UTC) when the task item was completed.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreatedDateTimeUtc

Indicates (in UTC) when the task item was created.

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### IsCompleted

Indicates whether the task item is completed.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this TaskItem. `Introduced in version 23.1.1.48`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Title

A brief description of the task item.

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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Task

The task to which this item is part of.

Type: **[Tasks](Projects.Todo.Tasks.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Projects.Todo.TaskItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Todo.TaskItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Todo_TaskItems

Domain API Entity Type: 
Projects_Todo_TaskItem

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Todo_TaskItems?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Todo_TaskItems?$top=10>

