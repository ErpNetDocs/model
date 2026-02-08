---
uid: Projects.Classic.ProjectRisks
---
# Projects.Classic.ProjectRisks


Contains risks, associated to projects.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.ProjectRisks  
Base Table: Prj_Project_Risks  
API access:  ReadWrite  

## Visualization
Display Format: {RiskName}  
Search Members: RiskName  
Name Member: RiskName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.Projects](Projects.Classic.Projects.md)  
Aggregate Root:  
[Projects.Classic.Projects](Projects.Classic.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreateDate](Projects.Classic.ProjectRisks.md#createdate) | date | The creation date of the project risk.`Required` `Default(Now)` `Filter(eq;ge;le)` 
| [Description](Projects.Classic.ProjectRisks.md#description) | string (max) __nullable__ | The description of this ProjectRisk. `Filter(like)` 
| [ImpactPercent](Projects.Classic.ProjectRisks.md#impactpercent) | decimal (3, 2) | The impact of the risk to the project, expressed as percentage of the total project value.`Required` `Default(0)` 
| [ProbabilityPercent](Projects.Classic.ProjectRisks.md#probabilitypercent) | decimal (3, 2) | The probability of the risk occurring.`Required` `Default(0)` 
| [ResolutionStrategy](Projects.Classic.ProjectRisks.md#resolutionstrategy) | string (max) __nullable__ | The strategy chosen to handle the risk`Filter(eq)` 
| [Resolved](Projects.Classic.ProjectRisks.md#resolved) | boolean | 1 if the risk is resolved`Required` `Default(false)` `Filter(eq)` 
| [ResolveDate](Projects.Classic.ProjectRisks.md#resolvedate) | date __nullable__ | The date on which the risk is resolved`Filter(eq;ge;le)` 
| [RiskName](Projects.Classic.ProjectRisks.md#riskname) | string (254) | The short name of the risk.`Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Project](Projects.Classic.ProjectRisks.md#project) | [Projects](Projects.Classic.Projects.md) | The project for which this risk applies. |
| [ResponsiblePerson](Projects.Classic.ProjectRisks.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | The person who is responsible for handling the risk |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.ProjectRisks.md#id) | guid |  
| [ObjectVersion](Projects.Classic.ProjectRisks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.ProjectRisks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Discussion | [ProjectRiskDiscussion](Projects.Classic.ProjectRiskDiscussion.md) | List of `ProjectRiskDiscussion`(Projects.Classic.ProjectRiskDiscussion.md) child objects, based on the `Projects.Classic.ProjectRiskDiscussion.ProjectRisk`(Projects.Classic.ProjectRiskDiscussion.md#projectrisk) back reference 


## Attribute Details

### CreateDate

The creation date of the project risk.`Required` `Default(Now)` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Description

The description of this ProjectRisk. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ImpactPercent

The impact of the risk to the project, expressed as percentage of the total project value.`Required` `Default(0)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ProbabilityPercent

The probability of the risk occurring.`Required` `Default(0)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ResolutionStrategy

The strategy chosen to handle the risk`Filter(eq)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Resolved

1 if the risk is resolved`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ResolveDate

The date on which the risk is resolved`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RiskName

The short name of the risk.`Required` `Filter(multi eq)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Project

The project for which this risk applies.

Type: **[Projects](Projects.Classic.Projects.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ResponsiblePerson

The person who is responsible for handling the risk

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Classic.ProjectRisks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.ProjectRisks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_ProjectRisks

Domain API Entity Type: 
Projects_Classic_ProjectRisk

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_ProjectRisks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_ProjectRisks?$top=10>

