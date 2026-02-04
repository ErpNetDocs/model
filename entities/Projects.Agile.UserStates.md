---
uid: Projects.Agile.UserStates
---
# Projects.Agile.UserStates


Workflow states for the case categories

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.UserStates  
Base Table: Apm_User_States  
Introduced In Version: 25.1.0.96  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.UserStates](Projects.Agile.UserStates.md)  
  * [Projects.Agile.UserStateCaseCategories](Projects.Agile.UserStateCaseCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Projects.Agile.UserStates.md#description) | [MultilanguageString (256)](../data-types.md#multilanguagestring) __nullable__ | Short explanation for this state, visible to users when selected. 
| [IsActive](Projects.Agile.UserStates.md#isactive) | boolean | Specifies whether the user state can be set to cases. 
| [Name](Projects.Agile.UserStates.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the user state. 
| [Notes](Projects.Agile.UserStates.md#notes) | string (max) __nullable__ | Notes 
| [Ord](Projects.Agile.UserStates.md#ord) | int32 | Unique ordinal position of the state within the system state. 
| [SystemState](Projects.Agile.UserStates.md#systemstate) | [SystemState](Projects.Agile.UserStates.md#systemstate) | The system state, which this state extends. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.UserStates.md#id) | guid |  
| [ObjectVersion](Projects.Agile.UserStates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.UserStates.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.UserStates.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.UserStates.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.UserStates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| CaseCategories | [UserStateCaseCategories](Projects.Agile.UserStateCaseCategories.md) | List of `UserStateCaseCategory`(Projects.Agile.UserStateCaseCategories.md) child objects, based on the `Projects.Agile.UserStateCaseCategory.UserState`(Projects.Agile.UserStateCaseCategories.md#userstate) back reference 


## Attribute Details

### Description

Short explanation for this state, visible to users when selected.

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the user state can be set to cases.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Multi-language name of the user state.

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Ord

Unique ordinal position of the state within the system state.

Type: **int32**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetUserStateOrd( obj.SystemState)`

Front-End Recalc Expressions:  
`obj.SetUserStateOrd( obj.SystemState)`
### SystemState

The system state, which this state extends.

Type: **[SystemState](Projects.Agile.UserStates.md#systemstate)**  
Category: **System**  
Allowed values for the `SystemState`(Projects.Agile.Cases.md#systemstate) data attribute  
Allowed Values (Projects.Agile.CasesRepository.SystemState Enum Members)  

| Value | Description |
| ---- | --- |
| BACKLOG | The case is registered but not yet considered for work.. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'BACKLOG' |
| CONSIDER | The case is under evaluation for possible execution.. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'CONSIDER' |
| READY | The case is approved and ready to be started.. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'READY' |
| INPROGRESS | Work on the case is currently ongoing.. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'INPROGRESS' |
| WAITING | The case is paused, waiting for input or conditions.. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'WAITING' |
| RESOLVED | Work is completed; final review or confirmation may be pending.. Stored as '6'. <br /> Database Value: '6' <br /> Model Value: 5 <br /> Domain API Value: 'RESOLVED' |
| CLOSED | The case is finalized and officially closed.. Stored as '7'. <br /> Database Value: '7' <br /> Model Value: 6 <br /> Domain API Value: 'CLOSED' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
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

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Projects.Agile.UserStates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.UserStates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_UserStates

Domain API Entity Type: 
Projects_Agile_UserState

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_UserStates?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_UserStates?$top=10>

