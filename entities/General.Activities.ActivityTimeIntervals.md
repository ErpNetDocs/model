---
uid: General.Activities.ActivityTimeIntervals
---
# General.Activities.ActivityTimeIntervals Entity

**Namespace:** [General.Activities](General.Activities.md)  

History of work efforts for executing activities (timesheet). Entity: Cm_Activity_Time_Intervals

## Renames

Old name: **General.Contacts.ActivityTimeIntervals**  
New name: **General.Activities.ActivityTimeIntervals**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Id}: {ActivityId}_  
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
* [General.Activities.ActivityTimeIntervals](General.Activities.ActivityTimeIntervals.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](General.Activities.ActivityTimeIntervals.md#date) | date | The date on which the work was performed. `Required` `Filter(eq;ge;le)` 
| [DisplayText](General.Activities.ActivityTimeIntervals.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndTime](General.Activities.ActivityTimeIntervals.md#endtime) | time | The ending time of the time interval within 'Date'. `Required` `Filter(ge;le)` 
| [ExecutionCompletePercent](General.Activities.ActivityTimeIntervals.md#executioncompletepercent) | decimal (3, 2) | Percent of task completed. `Required` `Default(0)` `Filter(ge;le)` 
| [ExternalId](General.Activities.ActivityTimeIntervals.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Activities.ActivityTimeIntervals.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](General.Activities.ActivityTimeIntervals.md#id) | guid |  
| [Notes](General.Activities.ActivityTimeIntervals.md#notes) | string (254) __nullable__ | Notes for the time interval. 
| [ObjectVersion](General.Activities.ActivityTimeIntervals.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartTime](General.Activities.ActivityTimeIntervals.md#starttime) | time | The starting time of the time interval within 'Date'. `Required` `Filter(ge;le)` 
| [State](General.Activities.ActivityTimeIntervals.md#state) | [DocumentState](General.Activities.ActivityTimeIntervals.md#state) __nullable__ | The state of the primary activity in the moment the time interval was created. null when the state is unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](General.Activities.ActivityTimeIntervals.md#activity) | [Activities](General.Activities.Activities.md) | The activity for which the time interval is recorded. `Required` `Filter(multi eq)` |
| [Party](General.Activities.ActivityTimeIntervals.md#party) | [Parties](General.Contacts.Parties.md) | The party for which the time interval is recorded. `Required` `Filter(multi eq)` |
| [UserStatus](General.Activities.ActivityTimeIntervals.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user status of the primary activity in the moment the time interval was created. null when the user status is unknown. `Filter(multi eq)` |


## Attribute Details

### Date

The date on which the work was performed. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
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

### EndTime

The ending time of the time interval within 'Date'. `Required` `Filter(ge;le)`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExecutionCompletePercent

Percent of task completed. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.Activity.PlannedDurationMinutes ?? 0) == 0), 0, Min( 0.9, Round( Max( 0, ( obj.Transaction.Clone( ).Query( ).Where( ti => ( ti.Activity == obj.Activity)).ToList( ).Where( ti => ( ( ti != obj) AndAlso ( ti.Date.Add( ti.EndTime) <= obj.Date.Add( obj.EndTime)))).OrderBy( ti => ti.Date.Add( ti.EndTime)).Select( ti => ti.ExecutionCompletePercent).LastOrDefault( ) + Convert( ( Convert( ( obj.EndTime - obj.StartTime).TotalMinutes, Nullable`1) / Convert( obj.Activity.PlannedDurationMinutes, Nullable`1)), Decimal))), 2)))`
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

### Notes

Notes for the time interval.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartTime

The starting time of the time interval within 'Date'. `Required` `Filter(ge;le)`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### State

The state of the primary activity in the moment the time interval was created. null when the state is unknown.

_Type_: **[DocumentState](General.Activities.ActivityTimeIntervals.md#state) __nullable__**  
_Category_: **System**  
Enumeration of document system states  
_Allowed Values (General.Documents.DocumentState Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Activity

The activity for which the time interval is recorded. `Required` `Filter(multi eq)`

_Type_: **[Activities](General.Activities.Activities.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Party

The party for which the time interval is recorded. `Required` `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UserStatus

The user status of the primary activity in the moment the time interval was created. null when the user status is unknown. `Filter(multi eq)`

_Type_: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Activities.ActivityTimeIntervals erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Activities.ActivityTimeIntervals erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Activities_ActivityTimeIntervals

Domain API Entity Type: 
General_Activities_ActivityTimeInterval

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Activities_ActivityTimeIntervals?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Activities_ActivityTimeIntervals?$top=10>

