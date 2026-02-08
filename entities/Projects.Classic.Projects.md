---
uid: Projects.Classic.Projects
---
# Projects.Classic.Projects


Contains the planned, running and completed projects of the enterprises.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.Projects  
Base Table: Prj_Projects  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

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
| [Code](Projects.Classic.Projects.md#code) | string (16) | Short code for identification of projects.`Required` `Filter(eq;like)` `ORD` 
| [FinishDate](Projects.Classic.Projects.md#finishdate) | date __nullable__ | The drop dead date of the project, e.g. the date when the project should be finished. NULL means that the finish date is unknown.`Filter(eq;ge;le)` 
| [Name](Projects.Classic.Projects.md#name) | string (254) | The name of this Project. `Required` `Filter(eq;like)` 
| [Notes](Projects.Classic.Projects.md#notes) | string (max) __nullable__ | Notes for this Project. 
| [ProjectStatus](Projects.Classic.Projects.md#projectstatus) | [ProjectStatus](Projects.Classic.Projects.md#projectstatus) | Current project status. 0=New/Structuring, 10=Budgeting, 20=Panning, 30=Started, 40=Resolved(Completed), 45=Resolved(Cancelled), 50=Closed(Completed), 55=Closed(Cancelled)`Required` `Default(0)` `Filter(multi eq)` 
| [StartDate](Projects.Classic.Projects.md#startdate) | date __nullable__ | Expected date, when the execution of the tasks will start. NULL means that the start date is still unknown`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BudgetingCurrency](Projects.Classic.Projects.md#budgetingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency in which the project budget is calculated |
| [ClientParty](Projects.Classic.Projects.md#clientparty) | [Parties](General.Contacts.Parties.md) (nullable) | The external or internal client of the project |
| [EnterpriseCompany](Projects.Classic.Projects.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Project applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [ProjectManagerPerson](Projects.Classic.Projects.md#projectmanagerperson) | [Persons](General.Contacts.Persons.md) (nullable) | The project manager |
| [ProjectType](Projects.Classic.Projects.md#projecttype) | [ProjectTypes](Projects.Classic.ProjectTypes.md) | The project type defines the basic WBS and default tasks, etc. It is also used as baseline WBS, when combining reports for many projects |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.Projects.md#id) | guid |  
| [ObjectVersion](Projects.Classic.Projects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Classic.Projects.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Classic.Projects.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Classic.Projects.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Classic.Projects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Participants | [ProjectParticipants](Projects.Classic.ProjectParticipants.md) | List of `ProjectParticipant`(Projects.Classic.ProjectParticipants.md) child objects, based on the `Projects.Classic.ProjectParticipant.Project`(Projects.Classic.ProjectParticipants.md#project) back reference 
| Risks | [ProjectRisks](Projects.Classic.ProjectRisks.md) | List of `ProjectRisk`(Projects.Classic.ProjectRisks.md) child objects, based on the `Projects.Classic.ProjectRisk.Project`(Projects.Classic.ProjectRisks.md#project) back reference 
| WorkElements | [ProjectWorkElements](Projects.Classic.ProjectWorkElements.md) | List of `ProjectWorkElement`(Projects.Classic.ProjectWorkElements.md) child objects, based on the `Projects.Classic.ProjectWorkElement.Project`(Projects.Classic.ProjectWorkElements.md#project) back reference 


## Attribute Details

### Code

Short code for identification of projects.`Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### FinishDate

The drop dead date of the project, e.g. the date when the project should be finished. NULL means that the finish date is unknown.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of this Project. `Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Project.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProjectStatus

Current project status. 0=New/Structuring, 10=Budgeting, 20=Panning, 30=Started, 40=Resolved(Completed), 45=Resolved(Cancelled), 50=Closed(Completed), 55=Closed(Cancelled)`Required` `Default(0)` `Filter(multi eq)`

Type: **[ProjectStatus](Projects.Classic.Projects.md#projectstatus)**  
Category: **System**  
Allowed values for the `ProjectStatus`(Projects.Classic.Projects.md#projectstatus) data attribute  
Allowed Values (Projects.Classic.ProjectsRepository.ProjectStatus Enum Members)  

| Value | Description |
| ---- | --- |
| NewOrStructuring | NewOrStructuring value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'NewOrStructuring' |
| Budgeting | Budgeting value. Stored as 10. <br /> Database Value: 10 <br /> Model Value: 10 <br /> Domain API Value: 'Budgeting' |
| Planning | Planning value. Stored as 20. <br /> Database Value: 20 <br /> Model Value: 20 <br /> Domain API Value: 'Planning' |
| Started | Started value. Stored as 30. <br /> Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Started' |
| ResolvedCompleted | ResolvedCompleted value. Stored as 40. <br /> Database Value: 40 <br /> Model Value: 40 <br /> Domain API Value: 'ResolvedCompleted' |
| ResolvedCancelled | ResolvedCancelled value. Stored as 45. <br /> Database Value: 45 <br /> Model Value: 45 <br /> Domain API Value: 'ResolvedCancelled' |
| ClosedCompleted | ClosedCompleted value. Stored as 50. <br /> Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'ClosedCompleted' |
| ClosedCanceled | ClosedCanceled value. Stored as 55. <br /> Database Value: 55 <br /> Model Value: 55 <br /> Domain API Value: 'ClosedCanceled' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### StartDate

Expected date, when the execution of the tasks will start. NULL means that the start date is still unknown`Filter(eq;ge;le)`

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

### BudgetingCurrency

The currency in which the project budget is calculated

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ClientParty

The external or internal client of the project

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Project applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProjectManagerPerson

The project manager

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectType

The project type defines the basic WBS and default tasks, etc. It is also used as baseline WBS, when combining reports for many projects

Type: **[ProjectTypes](Projects.Classic.ProjectTypes.md)**  
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

