---
uid: Projects.Agile.CaseAssignmentRules
---
# Projects.Agile.CaseAssignmentRules Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Contains rules for automatically assigning cases to users based on the values of the case fields, such as project, project area, case category, system state, user state, etc. Entity: Apm_Case_Assignment_Rules (Introduced in version 25.1.3.5)

## Default Visualization
Default Display Text Format:  
_{RuleNo}: {AssignmentKind} {AssignToUser}_  
Default Search Members:  
__  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.CaseAssignmentRules](Projects.Agile.CaseAssignmentRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind) | [AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind) | Specifies the logic for determining who should be assigned to the case. If 'Specific User' is selected, the user specified in the 'Assign To User' field will be assigned. Otherwise, the assignee is determined based on predefined users responsible for the project, project area, case, and others. `Required` `Default("SUS")` `Filter(multi eq;like)` `Introduced in version 25.1.3.29` 
| [DisplayText](Projects.Agile.CaseAssignmentRules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Agile.CaseAssignmentRules.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.CaseAssignmentRules.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FromDate](Projects.Agile.CaseAssignmentRules.md#fromdate) | date __nullable__ | Starting date of rule validity. null means no from date restriction. `Filter(eq;ge;le)` 
| [Id](Projects.Agile.CaseAssignmentRules.md#id) | guid |  
| [IsActive](Projects.Agile.CaseAssignmentRules.md#isactive) | boolean | Indicates whether the current rule is active. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Projects.Agile.CaseAssignmentRules.md#notes) | string (max) __nullable__ | Additional information or comments related to the rule. `Filter(like)` 
| [ObjectVersion](Projects.Agile.CaseAssignmentRules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Priority](Projects.Agile.CaseAssignmentRules.md#priority) | [Priority](Projects.Agile.CaseAssignmentRules.md#priority) | Priority when multiple rules match the criteria. `Required` `Default("3")` `Filter(eq)` 
| [RuleNo](Projects.Agile.CaseAssignmentRules.md#ruleno) | int32 | Consecutive number of the rule. `Required` `Filter(eq)` `ORD` 
| [SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) | [SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) __nullable__ | The system state to which the rule applies. null means the rule applies to all user states. `Filter(multi eq)` 
| [ToDate](Projects.Agile.CaseAssignmentRules.md#todate) | date __nullable__ | Ending date (inclusive) of rule validity. null means that the rule is valid forever. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignToUser](Projects.Agile.CaseAssignmentRules.md#assigntouser) | [Users](Systems.Security.Users.md) (nullable) | The user who will be automatically assigned to the case when the rule conditions are matched. `Filter(multi eq)` |
| [CaseCategory](Projects.Agile.CaseAssignmentRules.md#casecategory) | [CaseCategories](Projects.Agile.CaseCategories.md) (nullable) | The case category to which the rule applies. null means the rule applies to all categories. `Filter(multi eq)` |
| [Project](Projects.Agile.CaseAssignmentRules.md#project) | [Projects](Projects.Agile.Projects.md) (nullable) | The project to which the rule applies. null means the rule applies to all projects. `Filter(multi eq)` |
| [ProjectArea](Projects.Agile.CaseAssignmentRules.md#projectarea) | [ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable) | The project area to which the rule applies. null means the rule applies to all project areas. `Filter(multi eq)` |
| [ProjectMilestone](Projects.Agile.CaseAssignmentRules.md#projectmilestone) | [ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable) | The project milestone to which the rule applies. null means the rule applies to all milestones. `Filter(multi eq)` |
| [StakeholderParty](Projects.Agile.CaseAssignmentRules.md#stakeholderparty) | [Parties](General.Contacts.Parties.md) (nullable) | The stakeholder party to which the rule applies. null means the rule applies to all parties. `Filter(multi eq)` |
| [UserState](Projects.Agile.CaseAssignmentRules.md#userstate) | [UserStates](Projects.Agile.UserStates.md) (nullable) | The user state to which the rule applies. null means the rule applies to all user states. `Filter(multi eq)` |


## Attribute Details

### AssignmentKind

Specifies the logic for determining who should be assigned to the case. If 'Specific User' is selected, the user specified in the 'Assign To User' field will be assigned. Otherwise, the assignee is determined based on predefined users responsible for the project, project area, case, and others. `Required` `Default("SUS")` `Filter(multi eq;like)` `Introduced in version 25.1.3.29`

_Type_: **[AssignmentKind](Projects.Agile.CaseAssignmentRules.md#assignmentkind)**  
_Category_: **System**  
Allowed values for the `AssignmentKind`(Projects.Agile.CaseAssignmentRules.md#assignmentkind) data attribute  
_Allowed Values (Projects.Agile.CaseAssignmentRulesRepository.AssignmentKind Enum Members)_  

| Value | Description |
| ---- | --- |
| AreaResponsible | Area Responsible. Stored as 'ARS'. <br /> _Database Value:_ 'ARS' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AreaResponsible' |
| ProjectResponsible | Project Responsible. Stored as 'PRS'. <br /> _Database Value:_ 'PRS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ProjectResponsible' |
| CaseOwner | Case Owner. Stored as 'COW'. <br /> _Database Value:_ 'COW' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'CaseOwner' |
| CurrentUser | Current User. Stored as 'CUS'. <br /> _Database Value:_ 'CUS' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'CurrentUser' |
| SpecificUser | Specific User. Stored as 'SUS'. <br /> _Database Value:_ 'SUS' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'SpecificUser' |

_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **SpecificUser**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### FromDate

Starting date of rule validity. null means no from date restriction. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the current rule is active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Additional information or comments related to the rule. `Filter(like)`

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

### Priority

Priority when multiple rules match the criteria. `Required` `Default("3")` `Filter(eq)`

_Type_: **[Priority](Projects.Agile.CaseAssignmentRules.md#priority)**  
_Category_: **System**  
Allowed values for the `Priority`(Projects.Agile.CaseAssignmentRules.md#priority) data attribute  
_Allowed Values (Projects.Agile.CaseAssignmentRulesRepository.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Highest | Highest. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Highest' |
| High | High. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'High' |
| Medium | Medium. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Medium' |
| Low | Low. Stored as '4'. <br /> _Database Value:_ '4' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Low' |
| Lowest | Lowest. Stored as '5'. <br /> _Database Value:_ '5' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Lowest' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Medium**  
_Show in UI_: **ShownByDefault**  

### RuleNo

Consecutive number of the rule. `Required` `Filter(eq)` `ORD`

_Type_: **int32**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SetRuleNo( )`

_Front-End Recalc Expressions:_  
`obj.SetRuleNo( )`
### SystemState

The system state to which the rule applies. null means the rule applies to all user states. `Filter(multi eq)`

_Type_: **[SystemState](Projects.Agile.CaseAssignmentRules.md#systemstate) __nullable__**  
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
_Show in UI_: **ShownByDefault**  

### ToDate

Ending date (inclusive) of rule validity. null means that the rule is valid forever. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AssignToUser

The user who will be automatically assigned to the case when the rule conditions are matched. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CaseCategory

The case category to which the rule applies. null means the rule applies to all categories. `Filter(multi eq)`

_Type_: **[CaseCategories](Projects.Agile.CaseCategories.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Project

The project to which the rule applies. null means the rule applies to all projects. `Filter(multi eq)`

_Type_: **[Projects](Projects.Agile.Projects.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectArea

The project area to which the rule applies. null means the rule applies to all project areas. `Filter(multi eq)`

_Type_: **[ProjectAreas](Projects.Agile.ProjectAreas.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectMilestone

The project milestone to which the rule applies. null means the rule applies to all milestones. `Filter(multi eq)`

_Type_: **[ProjectMilestones](Projects.Agile.ProjectMilestones.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StakeholderParty

The stakeholder party to which the rule applies. null means the rule applies to all parties. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UserState

The user state to which the rule applies. null means the rule applies to all user states. `Filter(multi eq)`

_Type_: **[UserStates](Projects.Agile.UserStates.md) (nullable)**  
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

