---
uid: Projects.Classic.Projects
---
# Projects.Classic.Projects Entity

**Namespace:** [Projects.Classic](Projects.Classic.md)  

Contains the planned, running and completed projects of the enterprises. Entity: Prj_Projects

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Classic.Projects](Projects.Classic.Projects.md)  
  * [Projects.Classic.ProjectParticipants](Projects.Classic.ProjectParticipants.md)  
  * [Projects.Classic.ProjectRisks](Projects.Classic.ProjectRisks.md)  
    * [Projects.Classic.ProjectRiskDiscussion](Projects.Classic.ProjectRiskDiscussion.md)  
  * [Projects.Classic.ProjectWorkElements](Projects.Classic.ProjectWorkElements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Projects.Classic.Projects.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](Projects.Classic.Projects.md#code) | string (16) | Short code for identification of projects. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Projects.Classic.Projects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Classic.Projects.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Classic.Projects.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FinishDate](Projects.Classic.Projects.md#finishdate) | date __nullable__ | The drop dead date of the project, e.g. the date when the project should be finished. null means that the finish date is unknown. `Filter(eq;ge;le)` 
| [Id](Projects.Classic.Projects.md#id) | guid |  
| [Name](Projects.Classic.Projects.md#name) | string (254) | The name of this Project. `Required` `Filter(eq;like)` 
| [Notes](Projects.Classic.Projects.md#notes) | string (max) __nullable__ | Notes for this Project. 
| [ObjectVersion](Projects.Classic.Projects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProjectStatus](Projects.Classic.Projects.md#projectstatus) | [ProjectStatus](Projects.Classic.Projects.md#projectstatus) | Current project status. 0=New/Structuring, 10=Budgeting, 20=Panning, 30=Started, 40=Resolved(Completed), 45=Resolved(Cancelled), 50=Closed(Completed), 55=Closed(Cancelled). `Required` `Default(0)` `Filter(multi eq)` 
| [StartDate](Projects.Classic.Projects.md#startdate) | date __nullable__ | Expected date, when the execution of the tasks will start. null means that the start date is still unknown. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BudgetingCurrency](Projects.Classic.Projects.md#budgetingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency in which the project budget is calculated. `Filter(multi eq)` |
| [ClientParty](Projects.Classic.Projects.md#clientparty) | [Parties](General.Contacts.Parties.md) (nullable) | The external or internal client of the project. `Filter(multi eq)` |
| [EnterpriseCompany](Projects.Classic.Projects.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Project applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [ProjectManagerPerson](Projects.Classic.Projects.md#projectmanagerperson) | [Persons](General.Contacts.Persons.md) (nullable) | The project manager. `Filter(multi eq)` |
| [ProjectType](Projects.Classic.Projects.md#projecttype) | [ProjectTypes](Projects.Classic.ProjectTypes.md) | The project type defines the basic WBS and default tasks, etc. It is also used as baseline WBS, when combining reports for many projects. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Participants | [ProjectParticipants](Projects.Classic.ProjectParticipants.md) | List of `ProjectParticipant`(Projects.Classic.ProjectParticipants.md) child objects, based on the `Projects.Classic.ProjectParticipant.Project`(Projects.Classic.ProjectParticipants.md#project) back reference 
| Risks | [ProjectRisks](Projects.Classic.ProjectRisks.md) | List of `ProjectRisk`(Projects.Classic.ProjectRisks.md) child objects, based on the `Projects.Classic.ProjectRisk.Project`(Projects.Classic.ProjectRisks.md#project) back reference 
| WorkElements | [ProjectWorkElements](Projects.Classic.ProjectWorkElements.md) | List of `ProjectWorkElement`(Projects.Classic.ProjectWorkElements.md) child objects, based on the `Projects.Classic.ProjectWorkElement.Project`(Projects.Classic.ProjectWorkElements.md#project) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Code

Short code for identification of projects. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
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

### FinishDate

The drop dead date of the project, e.g. the date when the project should be finished. null means that the finish date is unknown. `Filter(eq;ge;le)`

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

### Name

The name of this Project. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Project.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### ProjectStatus

Current project status. 0=New/Structuring, 10=Budgeting, 20=Panning, 30=Started, 40=Resolved(Completed), 45=Resolved(Cancelled), 50=Closed(Completed), 55=Closed(Cancelled). `Required` `Default(0)` `Filter(multi eq)`

_Type_: **[ProjectStatus](Projects.Classic.Projects.md#projectstatus)**  
_Category_: **System**  
Allowed values for the `ProjectStatus`(Projects.Classic.Projects.md#projectstatus) data attribute  
_Allowed Values (Projects.Classic.ProjectsRepository.ProjectStatus Enum Members)_  

| Value | Description |
| ---- | --- |
| NewOrStructuring | NewOrStructuring value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NewOrStructuring' |
| Budgeting | Budgeting value. Stored as 10. <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Budgeting' |
| Planning | Planning value. Stored as 20. <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'Planning' |
| Started | Started value. Stored as 30. <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Started' |
| ResolvedCompleted | ResolvedCompleted value. Stored as 40. <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'ResolvedCompleted' |
| ResolvedCancelled | ResolvedCancelled value. Stored as 45. <br /> _Database Value:_ 45 <br /> _Model Value:_ 45 <br /> _Domain API Value:_ 'ResolvedCancelled' |
| ClosedCompleted | ClosedCompleted value. Stored as 50. <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'ClosedCompleted' |
| ClosedCanceled | ClosedCanceled value. Stored as 55. <br /> _Database Value:_ 55 <br /> _Model Value:_ 55 <br /> _Domain API Value:_ 'ClosedCanceled' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### StartDate

Expected date, when the execution of the tasks will start. null means that the start date is still unknown. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BudgetingCurrency

The currency in which the project budget is calculated. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ClientParty

The external or internal client of the project. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Project applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ProjectManagerPerson

The project manager. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectType

The project type defines the basic WBS and default tasks, etc. It is also used as baseline WBS, when combining reports for many projects. `Required` `Filter(multi eq)`

_Type_: **[ProjectTypes](Projects.Classic.ProjectTypes.md)**  
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

[!list limit=1000 erp.entity=Projects.Classic.Projects erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.Projects erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_Projects

Domain API Entity Type: 
Projects_Classic_Project

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_Projects?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_Projects?$top=10>

