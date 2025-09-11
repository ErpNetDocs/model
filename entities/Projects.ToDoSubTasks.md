---
uid: Projects.ToDoSubTasks
---
# Projects.ToDoSubTasks Entity

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

Aggregate Parent:  
[Projects.ToDoTasks](Projects.ToDoTasks.md)  
Aggregate Root:  
[Projects.ToDoTasks](Projects.ToDoTasks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletedDateTimeUtc](Projects.ToDoSubTasks.md#completeddatetimeutc) | datetime __nullable__ | Indicates (in UTC) when the subtask was completed. `ReadOnly` 
| [CreatedDateTimeUtc](Projects.ToDoSubTasks.md#createddatetimeutc) | datetime | Indicates (in UTC) when the subtask was created. `Required` `Default(NowUtc)` `ReadOnly` 
| [DisplayText](Projects.ToDoSubTasks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.ToDoSubTasks.md#id) | guid |  
| [IsCompleted](Projects.ToDoSubTasks.md#iscompleted) | boolean |  
| [Name](Projects.ToDoSubTasks.md#name) | string (254) | A brief description of the task. `Required` 
| [ObjectVersion](Projects.ToDoSubTasks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ToDoTask](Projects.ToDoSubTasks.md#todotask) | [ToDoTasks](Projects.ToDoTasks.md) | The task to which this is sub-task. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### CompletedDateTimeUtc

Indicates (in UTC) when the subtask was completed. `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### CreatedDateTimeUtc

Indicates (in UTC) when the subtask was created. `Required` `Default(NowUtc)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### IsCompleted

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Name

A brief description of the task. `Required`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### ToDoTask

The task to which this is sub-task. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ToDoTasks](Projects.ToDoTasks.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


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

[!list limit=1000 erp.entity=Projects.ToDoSubTasks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.ToDoSubTasks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_ToDoSubTasks?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_ToDoSubTasks?$top=10>

