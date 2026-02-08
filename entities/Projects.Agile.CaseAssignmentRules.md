---
uid: Projects.Agile.CaseAssignmentRules
---
# Projects.Agile.CaseAssignmentRules


Contains rules for automatically assigning cases to users based on the values of the case fields, such as project, project area, case category, system state, user state, etc.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.CaseAssignmentRules  
Base Table: Apm_Case_Assignment_Rules  
Introduced In Version: 25.1.3.5  
API access:  ReadWrite  

## Visualization
Display Format: {RuleNo}: {AssignmentKind} {AssignToUser}  
Search Members:   
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.CaseAssignmentRules](Projects.Agile.CaseAssignmentRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind) | [AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind) | Specifies the logic for determining who should be assigned to the case. If 'Specific User' is selected, the user specified in the 'Assign To User' field will be assigned. Otherwise, the assignee is determined based on predefined users responsible for the project, project area, case, and others.`Required` `Default(&quot;SUS&quot;)` `Filter(multi eq;like)` `Introduced in version 25.1.3.29` 
| [FromDate](Projects.Agile.CaseAssignmentRules.md#fromdate) | date __nullable__ | Starting date of rule validity. NULL means no from date restriction.`Filter(eq;ge;le)` 
| [IsActive](Projects.Agile.CaseAssignmentRules.md#isactive) | boolean | Indicates whether the current rule is active.`Required` `Default(true)` `Filter(eq)` 
| [Notes](Projects.Agile.CaseAssignmentRules.md#notes) | string (max) __nullable__ | Additional information or comments related to the rule.`Filter(like)` 
| [Priority](Projects.Agile.CaseAssignmentRules.md#priority) | [Priority](Projects.Agile.CaseAssignmentRules.md#priority) | Priority when multiple rules match the criteria.`Required` `Default(&quot;3&quot;)` `Filter(eq)` 
| [RuleNo](Projects.Agile.CaseAssignmentRules.md#ruleno) | int32 | Consecutive number of the rule.`Required` `Filter(eq)` `ORD` 
| [SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) | [SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) __nullable__ | The system state to which the rule applies. NULL means the rule applies to all user states.`Filter(multi eq)` 
| [ToDate](Projects.Agile.CaseAssignmentRules.md#todate) | date __nullable__ | Ending date (inclusive) of rule validity. NULL means that the rule is valid forever.`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignToUser](Projects.Agile.CaseAssignmentRules.md#assigntouser) | [Users](Systems.Security.Users.md) (nullable) | The user who will be automatically assigned to the case when the rule conditions are matched. |
| [CaseCategory](Projects.Agile.CaseAssignmentRules.md#casecategory) | [CaseCategories](Projects.Agile.CaseCategories.md) (nullable) | The case category to which the rule applies. NULL means the rule applies to all categories. |
| [Project](Projects.Agile.CaseAssignmentRules.md#project) | [Projects](Projects.Agile.Projects.md) (nullable) | The project to which the rule applies. NULL means the rule applies to all projects. |
| [ProjectArea](Projects.Agile.CaseAssignmentRules.md#projectarea) | [ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable) | The project area to which the rule applies. NULL means the rule applies to all project areas. |
| [ProjectMilestone](Projects.Agile.CaseAssignmentRules.md#projectmilestone) | [ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable) | The project milestone to which the rule applies. NULL means the rule applies to all milestones. |
| [StakeholderParty](Projects.Agile.CaseAssignmentRules.md#stakeholderparty) | [Parties](General.Contacts.Parties.md) (nullable) | The stakeholder party to which the rule applies. NULL means the rule applies to all parties. |
| [UserState](Projects.Agile.CaseAssignmentRules.md#userstate) | [UserStates](Projects.Agile.UserStates.md) (nullable) | The user state to which the rule applies. NULL means the rule applies to all user states. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.CaseAssignmentRules.md#id) | guid |  
| [ObjectVersion](Projects.Agile.CaseAssignmentRules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.CaseAssignmentRules.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.CaseAssignmentRules.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.CaseAssignmentRules.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.CaseAssignmentRules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AssignmentKind

Specifies the logic for determining who should be assigned to the case. If 'Specific User' is selected, the user specified in the 'Assign To User' field will be assigned. Otherwise, the assignee is determined based on predefined users responsible for the project, project area, case, and others.`Required` `Default(&quot;SUS&quot;)` `Filter(multi eq;like)` `Introduced in version 25.1.3.29`

Type: **[AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind)**  
Category: **System**  
Allowed values for the `AssignmentKind`(Projects.Agile.CaseAssignmentRules.md#assignmentkind) data attribute  
Allowed Values (Projects.Agile.CaseAssignmentRulesRepository.AssignmentKind Enum Members)  

| Value | Description |
| ---- | --- |
| AreaResponsible | Area Responsible. Stored as 'ARS'. <br /> Database Value: 'ARS' <br /> Model Value: 0 <br /> Domain API Value: 'AreaResponsible' |
| ProjectResponsible | Project Responsible. Stored as 'PRS'. <br /> Database Value: 'PRS' <br /> Model Value: 1 <br /> Domain API Value: 'ProjectResponsible' |
| CaseOwner | Case Owner. Stored as 'COW'. <br /> Database Value: 'COW' <br /> Model Value: 2 <br /> Domain API Value: 'CaseOwner' |
| CurrentUser | Current User. Stored as 'CUS'. <br /> Database Value: 'CUS' <br /> Model Value: 3 <br /> Domain API Value: 'CurrentUser' |
| SpecificUser | Specific User. Stored as 'SUS'. <br /> Database Value: 'SUS' <br /> Model Value: 4 <br /> Domain API Value: 'SpecificUser' |

Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Default Value: **SpecificUser**  
Show in UI: **ShownByDefault**  

### FromDate

Starting date of rule validity. NULL means no from date restriction.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current rule is active.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments related to the rule.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Priority

Priority when multiple rules match the criteria.`Required` `Default(&quot;3&quot;)` `Filter(eq)`

Type: **[Priority](Projects.Agile.CaseAssignmentRules.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Projects.Agile.CaseAssignmentRules.md#priority) data attribute  
Allowed Values (Projects.Agile.CaseAssignmentRulesRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Highest | Highest. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'Highest' |
| High | High. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'High' |
| Medium | Medium. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'Medium' |
| Low | Low. Stored as '4'. <br /> Database Value: '4' <br /> Model Value: 3 <br /> Domain API Value: 'Low' |
| Lowest | Lowest. Stored as '5'. <br /> Database Value: '5' <br /> Model Value: 4 <br /> Domain API Value: 'Lowest' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Medium**  
Show in UI: **ShownByDefault**  

### RuleNo

Consecutive number of the rule.`Required` `Filter(eq)` `ORD`

Type: **int32**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetRuleNo( )`

Front-End Recalc Expressions:  
`obj.SetRuleNo( )`
### SystemState

The system state to which the rule applies. NULL means the rule applies to all user states.`Filter(multi eq)`

Type: **[SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) __nullable__**  
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
Show in UI: **ShownByDefault**  

### ToDate

Ending date (inclusive) of rule validity. NULL means that the rule is valid forever.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### AssignToUser

The user who will be automatically assigned to the case when the rule conditions are matched.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CaseCategory

The case category to which the rule applies. NULL means the rule applies to all categories.

Type: **[CaseCategories](Projects.Agile.CaseCategories.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Project

The project to which the rule applies. NULL means the rule applies to all projects.

Type: **[Projects](Projects.Agile.Projects.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectArea

The project area to which the rule applies. NULL means the rule applies to all project areas.

Type: **[ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectMilestone

The project milestone to which the rule applies. NULL means the rule applies to all milestones.

Type: **[ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StakeholderParty

The stakeholder party to which the rule applies. NULL means the rule applies to all parties.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UserState

The user state to which the rule applies. NULL means the rule applies to all user states.

Type: **[UserStates](Projects.Agile.UserStates.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Agile.CaseAssignmentRules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.CaseAssignmentRules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_CaseAssignmentRules

Domain API Entity Type: 
Projects_Agile_CaseAssignmentRule

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_CaseAssignmentRules?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_CaseAssignmentRules?$top=10>

