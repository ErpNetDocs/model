---
uid: Projects.Agile.Cases
---
# Projects.Agile.Cases Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Case in a project. Used to track work progress. Entity: Apm_Cases (Introduced in version 24.1.1.86)

## Default Visualization
Default Display Text Format:  
_{Number}: {Title:T}_  
Default Search Members:  
_Number; Title_  
Code Data Member:  
_Number_  
Name Data Member:  
_Title_  
Category:  _Documents_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _CaseCategoryId_  

## Track Changes  
Min level:  _4 - Track object attribute and blob changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Projects.Agile.Cases.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DueDate](Projects.Agile.Cases.md#duedate) | date __nullable__ | Specified when the case has specific due date. `Filter(ge;le)` 
| [DueTime](Projects.Agile.Cases.md#duetime) | time __nullable__ | Specified when the case has specific due time. `Filter(ge;le)` 
| [EstimatedTimeHours](Projects.Agile.Cases.md#estimatedtimehours) | decimal (8, 2) __nullable__ | Estimation of the required work effort in hours. 
| [ExternalId](Projects.Agile.Cases.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.Cases.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FullState](Projects.Agile.Cases.md#fullstate) | int32 | Full state of the case based on its system and user state. [ReadOnly] 
| [Id](Projects.Agile.Cases.md#id) | guid |  
| [InProgressTimeUTC](Projects.Agile.Cases.md#inprogresstimeutc) | datetime __nullable__ | Indicates the time (in UTC) when the case has changed to in-progress state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93` 
| [LoggedTime](Projects.Agile.Cases.md#loggedtime) | decimal (0, 0) | Total duration of the logged time for the case (in hours). [ReadOnly] 
| [Number](Projects.Agile.Cases.md#number) | int32 | The unique number of the Case. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` `Introduced in version 24.1.3.86` 
| [ObjectVersion](Projects.Agile.Cases.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Developments | [CaseDevelopments](Projects.Agile.CaseDevelopments.md) | List of `CaseDevelopment`(Projects.Agile.CaseDevelopments.md) child objects, based on the `Projects.Agile.CaseDevelopment.Case`(Projects.Agile.CaseDevelopments.md#case) back reference 


## Attribute Details

### ClosedTimeUTC

Indicates the time (in UTC) when the case was closed. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### ConsiderTimeUTC

Indicates the time (in UTC) when the case has changed to consider state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.1.39`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationTimeUtc

The exact date and time (in UTC) when the case was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **HiddenByDefault**  

### Description

Description of the required work. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DueDate

Specified when the case has specific due date. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DueTime

Specified when the case has specific due time. `Filter(ge;le)`

_Type_: **time __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### EstimatedTimeHours

Estimation of the required work effort in hours.

_Type_: **decimal (8, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### FullState

Full state of the case based on its system and user state. [ReadOnly]

_Type_: **int32**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InProgressTimeUTC

Indicates the time (in UTC) when the case has changed to in-progress state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### LoggedTime

Total duration of the logged time for the case (in hours). [ReadOnly]

_Type_: **decimal (0, 0)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **ShownByDefault**  

### Number

The unique number of the Case. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` `Introduced in version 24.1.3.86`

_Type_: **int32**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Priority

Priority of the case, on a scale from 1 (highest) to 7 (lowest). `Required` `Default(7)` `Filter(eq)`

_Type_: **[Priority](Projects.Agile.Cases.md#priority)**  
_Category_: **System**  
Allowed values for the `Priority`(Projects.Agile.Cases.md#priority) data attribute  
_Allowed Values (Projects.Agile.CasesRepository.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Highest | Highest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Highest' |
| Two | Two value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Three' |
| Four | Four value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Four' |
| Five | Five value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Five' |
| Six | Six value. Stored as 6. <br /> _Database Value:_ 6 <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Six' |
| Lowest | Lowest value. Stored as 7. <br /> _Database Value:_ 7 <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Lowest' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **7**  
_Show in UI_: **ShownByDefault**  

### ReadyTimeUTC

Indicates the time (in UTC) when the case has become ready for execution. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### ResolvedTimeUTC

Indicates the time (in UTC) when the case was resolved. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### StoryPoints

When not null, represents the estimated effort to complete the case, measured in whole numbers. Used for sprint planning and velocity tracking. Higher values indicate greater complexity or workload. `Filter(eq;ge;le)` `Introduced in version 26.1.4.53`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SystemState

The base state of the case. `Required` `Default("1")` `Filter(multi eq)` `ReadOnly`

_Type_: **[SystemState](Projects.Agile.Cases.md#systemstate)**  
_Category_: **System**  
Allowed values for the `SystemState`(Projects.Agile.Cases.md#systemstate) data attribute  
_Allowed Values (Projects.Agile.CasesRepository.SystemState Enum Members)_  

| Value | Description |
| ---- | --- |
| BACKLOG | The case is registered but not yet considered for work.. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'BACKLOG' |
| CONSIDER | The case is under evaluation for possible execution.. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CONSIDER' |
| READY | The case is approved and ready to be started.. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'READY' |
| INPROGRESS | Work on the case is currently ongoing.. Stored as '4'. <br /> _Database Value:_ '4' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'INPROGRESS' |
| WAITING | The case is paused, waiting for input or conditions.. Stored as '5'. <br /> _Database Value:_ '5' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'WAITING' |
| RESOLVED | Work is completed; final review or confirmation may be pending.. Stored as '6'. <br /> _Database Value:_ '6' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'RESOLVED' |
| CLOSED | The case is finalized and officially closed.. Stored as '7'. <br /> _Database Value:_ '7' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'CLOSED' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **BACKLOG**  
_Show in UI_: **HiddenByDefault**  

### Title

Case short title. `Required` `Filter(like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### WaitingTimeUTC

Indicates the time (in UTC) when the case has changed to waiting state. `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.0.93`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### AssignedToUser

The internal user to which the case is assigned. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.DetermineAssignToUser( obj.SystemState, obj.Project, obj.CaseCategory, obj.ProjectArea, obj.ProjectMilestone, obj.StakeholderParty, obj.UserState).IfNullThen( obj.AssignedToUser)`
### CaseCategory

The category of the case. This also determines the workflow for the case. `Required` `Filter(multi eq)`

_Type_: **[CaseCategories](Projects.Agile.CaseCategories.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DuplicateOfCase

References the original case that this case duplicates. Used to identify and link duplicate cases within the system, ensuring better case management and avoiding redundant processing. `Filter(multi eq)` `Introduced in version 25.1.3.24`

_Type_: **[Cases](Projects.Agile.Cases.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### OwnerUser

The user responsible for managing and overseeing the case. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.76`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Parent

Specified when this is a sub-case to another case. `Filter(multi eq)`

_Type_: **[Cases](Projects.Agile.Cases.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Project

The project to which the case is assigned. `Required` `Filter(multi eq)`

_Type_: **[Projects](Projects.Agile.Projects.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectArea

The are to which the case is assigned. `Filter(multi eq)`

_Type_: **[ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectMilestone

Determines the milestone for which the case must be resolved. `Filter(multi eq)`

_Type_: **[ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SocialGroup

Specified, when the case is assigned to a group of users. `Filter(multi eq)`

_Type_: **[Groups](Communities.Social.Groups.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Sprint

The sprint to which the case is currently assigned. Many cases can be linked to the same sprint, but a single case can belong to only one sprint at a time. If the value is null, the case is not currently assigned to any sprint (i.e., it is in the backlog and not part of timeboxed work). `Filter(multi eq)` `Introduced in version 26.1.4.33`

_Type_: **[Sprints](Projects.Agile.Sprints.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StakeholderParty

The stakeholder with vested interest in the outcome of the case. Usually used to denote an important external stakeholder (like Customer). `Filter(multi eq)` `Introduced in version 25.1.2.70`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UserState

The user-defined sub-state of the case. `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.0.97`

_Type_: **[UserStates](Projects.Agile.UserStates.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  


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

