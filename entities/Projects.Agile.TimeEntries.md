---
uid: Projects.Agile.TimeEntries
---
# Projects.Agile.TimeEntries Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Contains entries about the time spent working on cases. Entity: Apm_Time_Entries (Introduced in version 25.1.2.78)

## Default Visualization
Default Display Text Format:  
_{Date:d} {StartTime:hh\:mm} - {EndTime:hh\:mm}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.TimeEntries](Projects.Agile.TimeEntries.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](Projects.Agile.TimeEntries.md#date) | date | The date for which the time entry is created. `Required` `Filter(eq;ge;le)` `ORD` 
| [DisplayText](Projects.Agile.TimeEntries.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DurationHours](Projects.Agile.TimeEntries.md#durationhours) | decimal (0, 0) | Total duration of the logged time (in hours). [ReadOnly] 
| [EndTime](Projects.Agile.TimeEntries.md#endtime) | time __nullable__ | The ending time of the logged work. Stored in the local time zone of the user. Empty value when the work is still in progress. `Filter(eq;ge;le)` 
| [ExternalId](Projects.Agile.TimeEntries.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.TimeEntries.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Agile.TimeEntries.md#id) | guid |  
| [Notes](Projects.Agile.TimeEntries.md#notes) | string (max) __nullable__ | Notes. `Filter(like)` 
| [ObjectVersion](Projects.Agile.TimeEntries.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartTime](Projects.Agile.TimeEntries.md#starttime) | time | The start time of the logged work. Stored in the local time zone of the user. `Required` `Filter(eq;ge;le)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Case](Projects.Agile.TimeEntries.md#case) | [Cases](Projects.Agile.Cases.md) | The case for which the time is recorded. `Required` `Filter(multi eq)` |
| [User](Projects.Agile.TimeEntries.md#user) | [Users](Systems.Security.Users.md) | The user for whom the time is recorded. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### Date

The date for which the time entry is created. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DurationHours

Total duration of the logged time (in hours). [ReadOnly]

_Type_: **decimal (0, 0)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **ShownByDefault**  

### EndTime

The ending time of the logged work. Stored in the local time zone of the user. Empty value when the work is still in progress. `Filter(eq;ge;le)`

_Type_: **time __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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

### Notes

Notes. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### StartTime

The start time of the logged work. Stored in the local time zone of the user. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Case

The case for which the time is recorded. `Required` `Filter(multi eq)`

_Type_: **[Cases](Projects.Agile.Cases.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user for whom the time is recorded. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Projects.Agile.TimeEntries erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.TimeEntries erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_TimeEntries

Domain API Entity Type: 
Projects_Agile_TimeEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_TimeEntries?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_TimeEntries?$top=10>

