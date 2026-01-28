---
uid: Projects.Agile.Cases
---
# Projects.Agile.Cases


Case in a project. Used to track work progress.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.Cases  
Base Table: Apm_Cases  
Introduced In Version: 24.1.1.86  
API access:  ReadWrite  

## Visualization
Display Format: {Number}: {Title:T}  
Search Members: Number; Title  
Code Member: Number  
Name Member: Title  
Category:  Documents  
Show in UI:  ShownByDefault  
Layout category By:  CaseCategoryId  

## Track Changes  
Min level:  4 - Track object attribute and blob changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.Cases](Projects.Agile.Cases.md)  
  * [Projects.Agile.CaseDevelopments](Projects.Agile.CaseDevelopments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ClosedTimeUTC](Projects.Agile.Cases.md#closedtimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case was closed. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [ConsiderTimeUTC](Projects.Agile.Cases.md#considertimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case has changed to consider state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.1.39` 
| [CreationTimeUtc](Projects.Agile.Cases.md#creationtimeutc) | datetime | The exact date and time (in UTC) when the case was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [Description](Projects.Agile.Cases.md#description) | string (max) __nullable__ | Description of the required work. `Filter(like)` 
| [DueDate](Projects.Agile.Cases.md#duedate) | date __nullable__ | Specified when the case has specific due date. `Filter(ge;le)` 
| [DueTime](Projects.Agile.Cases.md#duetime) | time __nullable__ | Specified when the case has specific due time. `Filter(ge;le)` 
| [EstimatedTimeHours](Projects.Agile.Cases.md#estimatedtimehours) | decimal (8, 2) __nullable__ | Estimation of the required work effort in hours. 
| [FullState](Projects.Agile.Cases.md#fullstate) | int32 | Full state of the case based on its system and user state. [ReadOnly] 
| [InProgressTimeUTC](Projects.Agile.Cases.md#inprogresstimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case has changed to in-progress state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [LoggedTime](Projects.Agile.Cases.md#loggedtime) | decimal (0, 0) | Total duration of the logged time for the case (in hours). [ReadOnly] 
| [Number](Projects.Agile.Cases.md#number) | int32 | The unique number of the Case. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` `Introduced in version 24.1.3.86` 
| [Priority](Projects.Agile.Cases.md#priority) | [Priority](Projects.Agile.Cases.md#priority) | Priority of the case, on a scale from 1 (highest) to 7 (lowest). `Required` `Default(7)` `Filter(eq)` 
| [ReadyTimeUTC](Projects.Agile.Cases.md#readytimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case has become ready for execution. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [ResolvedTimeUTC](Projects.Agile.Cases.md#resolvedtimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case was resolved. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [StoryPoints](Projects.Agile.Cases.md#storypoints) | int32 __nullable__ | When not null, represents the estimated effort to complete the case, measured in whole numbers. Used for sprint planning and velocity tracking. Higher values indicate greater complexity or workload. `Filter(eq;ge;le)` `Introduced in version 26.1.4.53` 
| [SystemState](Projects.Agile.Cases.md#systemstate) | [SystemState](Projects.Agile.Cases.md#systemstate) | The base state of the case. `Required` `Default("1")` `Filter(multi eq)` `ReadOnly` 
| [Title](Projects.Agile.Cases.md#title) | string (128) | Case short title. `Required` `Filter(like)` 
| [WaitingTimeUTC](Projects.Agile.Cases.md#waitingtimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case has changed to waiting state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToUser](Projects.Agile.Cases.md#assignedtouser) | [Users](Systems.Security.Users.md) (nullable) | The internal user to which the case is assigned. `Filter(multi eq)` |
| [CaseCategory](Projects.Agile.Cases.md#casecategory) | [CaseCategories](Projects.Agile.CaseCategories.md) | The category of the case. This also determines the workflow for the case. `Required` `Filter(multi eq)` |
| [DuplicateOfCase](Projects.Agile.Cases.md#duplicateofcase) | [Cases](Projects.Agile.Cases.md) (nullable) | References the original case that this case duplicates. Used to identify and link duplicate cases within the system, ensuring better case management and avoiding redundant processing. `Filter(multi eq)` `Introduced in version 25.1.3.24` |
| [OwnerUser](Projects.Agile.Cases.md#owneruser) | [Users](Systems.Security.Users.md) | The user responsible for managing and overseeing the case. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76` |
| [Parent](Projects.Agile.Cases.md#parent) | [Cases](Projects.Agile.Cases.md) (nullable) | Specified when this is a sub-case to another case. `Filter(multi eq)` |
| [Project](Projects.Agile.Cases.md#project) | [Projects](Projects.Agile.Projects.md) | The project to which the case is assigned. `Required` `Filter(multi eq)` |
| [ProjectArea](Projects.Agile.Cases.md#projectarea) | [ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable) | The are to which the case is assigned. `Filter(multi eq)` |
| [ProjectMilestone](Projects.Agile.Cases.md#projectmilestone) | [ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable) | Determines the milestone for which the case must be resolved. `Filter(multi eq)` |
| [SocialGroup](Projects.Agile.Cases.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | Specified, when the case is assigned to a group of users. `Filter(multi eq)` |
| [Sprint](Projects.Agile.Cases.md#sprint) | [Sprints](Projects.Agile.Sprints.md) (nullable) | The sprint to which the case is currently assigned. Many cases can be linked to the same sprint, but a single case can belong to only one sprint at a time. If the value is null, the case is not currently assigned to any sprint (i.e., it is in the backlog and not part of timeboxed work). `Filter(multi eq)` `Introduced in version 26.1.4.33` |
| [StakeholderParty](Projects.Agile.Cases.md#stakeholderparty) | [Parties](General.Contacts.Parties.md) (nullable) | The stakeholder with vested interest in the outcome of the case. Usually used to denote an important external stakeholder (like Customer). `Filter(multi eq)` `Introduced in version 25.1.2.70` |
| [UserState](Projects.Agile.Cases.md#userstate) | [UserStates](Projects.Agile.UserStates.md) (nullable) | The user-defined sub-state of the case. `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.0.97` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.Cases.md#id) | guid |  
| [ObjectVersion](Projects.Agile.Cases.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.Cases.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.Cases.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.Cases.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.Cases.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Developments | [CaseDevelopments](Projects.Agile.CaseDevelopments.md) | List of `CaseDevelopment`(Projects.Agile.CaseDevelopments.md) child objects, based on the `Projects.Agile.CaseDevelopment.Case`(Projects.Agile.CaseDevelopments.md#case) back reference 


## Attribute Details

### ClosedTimeUTC

Indicates the time (in UTC) when the case was closed. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ConsiderTimeUTC

Indicates the time (in UTC) when the case has changed to consider state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.1.39`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the case was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **HiddenByDefault**  

### Description

Description of the required work. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### DueDate

Specified when the case has specific due date. `Filter(ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DueTime

Specified when the case has specific due time. `Filter(ge;le)`

Type: **time __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EstimatedTimeHours

Estimation of the required work effort in hours.

Type: **decimal (8, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FullState

Full state of the case based on its system and user state. [ReadOnly]

Type: **int32**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### InProgressTimeUTC

Indicates the time (in UTC) when the case has changed to in-progress state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### LoggedTime

Total duration of the logged time for the case (in hours). [ReadOnly]

Type: **decimal (0, 0)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **ShownByDefault**  

### Number

The unique number of the Case. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` `Introduced in version 24.1.3.86`

Type: **int32**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Priority

Priority of the case, on a scale from 1 (highest) to 7 (lowest). `Required` `Default(7)` `Filter(eq)`

Type: **[Priority](Projects.Agile.Cases.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Projects.Agile.Cases.md#priority) data attribute  
Allowed Values (Projects.Agile.CasesRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Highest | Highest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Highest' |
| Two | Two value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Three' |
| Four | Four value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'Four' |
| Five | Five value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Five' |
| Six | Six value. Stored as 6. <br /> Database Value: 6 <br /> Model Value: 6 <br /> Domain API Value: 'Six' |
| Lowest | Lowest value. Stored as 7. <br /> Database Value: 7 <br /> Model Value: 7 <br /> Domain API Value: 'Lowest' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **7**  
Show in UI: **ShownByDefault**  

### ReadyTimeUTC

Indicates the time (in UTC) when the case has become ready for execution. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ResolvedTimeUTC

Indicates the time (in UTC) when the case was resolved. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### StoryPoints

When not null, represents the estimated effort to complete the case, measured in whole numbers. Used for sprint planning and velocity tracking. Higher values indicate greater complexity or workload. `Filter(eq;ge;le)` `Introduced in version 26.1.4.53`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SystemState

The base state of the case. `Required` `Default("1")` `Filter(multi eq)` `ReadOnly`

Type: **[SystemState](Projects.Agile.Cases.md#systemstate)**  
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
Supports Order By: **False**  
Default Value: **BACKLOG**  
Show in UI: **HiddenByDefault**  

### Title

Case short title. `Required` `Filter(like)`

Type: **string (128)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### WaitingTimeUTC

Indicates the time (in UTC) when the case has changed to waiting state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

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

### AssignedToUser

The internal user to which the case is assigned. `Filter(multi eq)`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineAssignToUser( obj.SystemState, obj.Project, obj.CaseCategory, obj.ProjectArea, obj.ProjectMilestone, obj.StakeholderParty, obj.UserState).IfNullThen( obj.AssignedToUser)`
### CaseCategory

The category of the case. This also determines the workflow for the case. `Required` `Filter(multi eq)`

Type: **[CaseCategories](Projects.Agile.CaseCategories.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DuplicateOfCase

References the original case that this case duplicates. Used to identify and link duplicate cases within the system, ensuring better case management and avoiding redundant processing. `Filter(multi eq)` `Introduced in version 25.1.3.24`

Type: **[Cases](Projects.Agile.Cases.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### OwnerUser

The user responsible for managing and overseeing the case. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76`

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Parent

Specified when this is a sub-case to another case. `Filter(multi eq)`

Type: **[Cases](Projects.Agile.Cases.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Project

The project to which the case is assigned. `Required` `Filter(multi eq)`

Type: **[Projects](Projects.Agile.Projects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectArea

The are to which the case is assigned. `Filter(multi eq)`

Type: **[ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectMilestone

Determines the milestone for which the case must be resolved. `Filter(multi eq)`

Type: **[ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SocialGroup

Specified, when the case is assigned to a group of users. `Filter(multi eq)`

Type: **[Groups](Communities.Social.Groups.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Sprint

The sprint to which the case is currently assigned. Many cases can be linked to the same sprint, but a single case can belong to only one sprint at a time. If the value is null, the case is not currently assigned to any sprint (i.e., it is in the backlog and not part of timeboxed work). `Filter(multi eq)` `Introduced in version 26.1.4.33`

Type: **[Sprints](Projects.Agile.Sprints.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StakeholderParty

The stakeholder with vested interest in the outcome of the case. Usually used to denote an important external stakeholder (like Customer). `Filter(multi eq)` `Introduced in version 25.1.2.70`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UserState

The user-defined sub-state of the case. `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.0.97`

Type: **[UserStates](Projects.Agile.UserStates.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Projects.Agile.Cases erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.Cases erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_Cases

Domain API Entity Type: 
Projects_Agile_Case

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_Cases?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_Cases?$top=10>

