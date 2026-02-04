---
uid: General.Activities.ActivityTimeIntervals
---
# General.Activities.ActivityTimeIntervals


History of work efforts for executing activities (timesheet).

## General
Namespace: [General.Activities](General.Activities.md)  
Repository: General.Activities.ActivityTimeIntervals  
Base Table: Cm_Activity_Time_Intervals  
API access:  ReadWrite  

## Renames

Old name: General.Contacts.ActivityTimeIntervals  
New name: General.Activities.ActivityTimeIntervals  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Id}: {ActivityId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Activities.ActivityTimeIntervals](General.Activities.ActivityTimeIntervals.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](General.Activities.ActivityTimeIntervals.md#date) | date | The date on which the work was performed. `Required` `Filter(eq;ge;le)` 
| [EndTime](General.Activities.ActivityTimeIntervals.md#endtime) | time | The ending time of the time interval within 'Date'. `Required` `Filter(ge;le)` 
| [ExecutionCompletePercent](General.Activities.ActivityTimeIntervals.md#executioncompletepercent) | decimal (3, 2) | Percent of task completed. `Required` `Default(0)` `Filter(ge;le)` 
| [Notes](General.Activities.ActivityTimeIntervals.md#notes) | string (254) __nullable__ | Notes for the time interval. 
| [StartTime](General.Activities.ActivityTimeIntervals.md#starttime) | time | The starting time of the time interval within 'Date'. `Required` `Filter(ge;le)` 
| [State](General.Activities.ActivityTimeIntervals.md#state) | [DocumentState](General.Activities.ActivityTimeIntervals.md#state) __nullable__ | The state of the primary activity in the moment the time interval was created. null when the state is unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](General.Activities.ActivityTimeIntervals.md#activity) | [Activities](General.Activities.Activities.md) | The activity for which the time interval is recorded. `Required` `Filter(multi eq)` |
| [Party](General.Activities.ActivityTimeIntervals.md#party) | [Parties](General.Contacts.Parties.md) | The party for which the time interval is recorded. `Required` `Filter(multi eq)` |
| [UserStatus](General.Activities.ActivityTimeIntervals.md#userstatus) | [DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable) | The user status of the primary activity in the moment the time interval was created. null when the user status is unknown. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Activities.ActivityTimeIntervals.md#id) | guid |  
| [ObjectVersion](General.Activities.ActivityTimeIntervals.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Activities.ActivityTimeIntervals.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Activities.ActivityTimeIntervals.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Activities.ActivityTimeIntervals.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Activities.ActivityTimeIntervals.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Date

The date on which the work was performed. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EndTime

The ending time of the time interval within 'Date'. `Required` `Filter(ge;le)`

Type: **time**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionCompletePercent

Percent of task completed. `Required` `Default(0)` `Filter(ge;le)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.Activity.PlannedDurationMinutes ?? 0) == 0), 0, Min( 0.9, Round( Max( 0, ( obj.Transaction.Clone( ).Query( ).Where( ti => ( ti.Activity == obj.Activity)).ToList( ).Where( ti => ( ( ti != obj) AndAlso ( ti.Date.Add( ti.EndTime) <= obj.Date.Add( obj.EndTime)))).OrderBy( ti => ti.Date.Add( ti.EndTime)).Select( ti => ti.ExecutionCompletePercent).LastOrDefault( ) + Convert( ( Convert( ( obj.EndTime - obj.StartTime).TotalMinutes, Nullable`1) / Convert( obj.Activity.PlannedDurationMinutes, Nullable`1)), Decimal))), 2)))`
### Notes

Notes for the time interval.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### StartTime

The starting time of the time interval within 'Date'. `Required` `Filter(ge;le)`

Type: **time**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### State

The state of the primary activity in the moment the time interval was created. null when the state is unknown.

Type: **[DocumentState](General.Activities.ActivityTimeIntervals.md#state) __nullable__**  
Category: **System**  
Enumeration of document system states  
Allowed Values (General.Documents.DocumentState Enum Members)  

| Value | Description |
| ---- | --- |
| New | New document, just created. Can be edited. (Stored as 0). <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Adjustment | Document which adjusts other released documents. (Stored as 5). <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Adjustment' |
| Planned | Planned by the system for future releasing. (Stored as 10). <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Planned' |
| FirmPlanned | Planned by operator for future releasing. (Stored as 20). <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'FirmPlanned' |
| Released | Released document. Changes can be applied only through adjustment documents. (Stored as 30). <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Released' |
| Completed | Work has completed. (Stored as 40). <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'Completed' |
| Closed | The document is audited and closed. Adjustments are not allowed, but reopening is allowed. (Stored as 50). <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Closed' |

Supported Filters: **NotFilterable**  
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

### Activity

The activity for which the time interval is recorded. `Required` `Filter(multi eq)`

Type: **[Activities](General.Activities.Activities.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

The party for which the time interval is recorded. `Required` `Filter(multi eq)`

Type: **[Parties](General.Contacts.Parties.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UserStatus

The user status of the primary activity in the moment the time interval was created. null when the user status is unknown. `Filter(multi eq)`

Type: **[DocumentTypeUserStatuses](Systems.Documents.DocumentTypeUserStatuses.md) (nullable)**  
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

