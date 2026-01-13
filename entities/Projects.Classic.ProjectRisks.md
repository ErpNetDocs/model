---
uid: Projects.Classic.ProjectRisks
---
# Projects.Classic.ProjectRisks Entity

**Namespace:** [Projects.Classic](Projects.Classic.md)  

Contains risks, associated to projects. Entity: Prj_Project_Risks

## Default Visualization
Default Display Text Format:  
_{RiskName}_  
Default Search Members:  
_RiskName_  
Name Data Member:  
_RiskName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.Projects](Projects.Classic.Projects.md)  
Aggregate Root:  
[Projects.Classic.Projects](Projects.Classic.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreateDate](Projects.Classic.ProjectRisks.md#createdate) | date | The creation date of the project risk. `Required` `Default(Now)` `Filter(eq;ge;le)` 
| [Description](Projects.Classic.ProjectRisks.md#description) | string (max) __nullable__ | The description of this ProjectRisk. `Filter(like)` 
| [DisplayText](Projects.Classic.ProjectRisks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.Classic.ProjectRisks.md#id) | guid |  
| [ImpactPercent](Projects.Classic.ProjectRisks.md#impactpercent) | decimal (3, 2) | The impact of the risk to the project, expressed as percentage of the total project value. `Required` `Default(0)` 
| [ObjectVersion](Projects.Classic.ProjectRisks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProbabilityPercent](Projects.Classic.ProjectRisks.md#probabilitypercent) | decimal (3, 2) | The probability of the risk occurring. `Required` `Default(0)` 
| [ResolutionStrategy](Projects.Classic.ProjectRisks.md#resolutionstrategy) | string (max) __nullable__ | The strategy chosen to handle the risk. `Filter(eq)` 
| [Resolved](Projects.Classic.ProjectRisks.md#resolved) | boolean | True if the risk is resolved. `Required` `Default(false)` `Filter(eq)` 
| [ResolveDate](Projects.Classic.ProjectRisks.md#resolvedate) | date __nullable__ | The date on which the risk is resolved. `Filter(eq;ge;le)` 
| [RiskName](Projects.Classic.ProjectRisks.md#riskname) | string (254) | The short name of the risk. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Project](Projects.Classic.ProjectRisks.md#project) | [Projects](Projects.Classic.Projects.md) | The project for which this risk applies. `Required` `Filter(multi eq)` `Owner` |
| [ResponsiblePerson](Projects.Classic.ProjectRisks.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | The person who is responsible for handling the risk. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Discussion | [ProjectRiskDiscussion](Projects.Classic.ProjectRiskDiscussion.md) | List of `ProjectRiskDiscussion`(Projects.Classic.ProjectRiskDiscussion.md) child objects, based on the `Projects.Classic.ProjectRiskDiscussion.ProjectRisk`(Projects.Classic.ProjectRiskDiscussion.md#projectrisk) back reference 


## Attribute Details

### CreateDate

The creation date of the project risk. `Required` `Default(Now)` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### Description

The description of this ProjectRisk. `Filter(like)`

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ImpactPercent

The impact of the risk to the project, expressed as percentage of the total project value. `Required` `Default(0)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProbabilityPercent

The probability of the risk occurring. `Required` `Default(0)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ResolutionStrategy

The strategy chosen to handle the risk. `Filter(eq)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Resolved

True if the risk is resolved. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ResolveDate

The date on which the risk is resolved. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RiskName

The short name of the risk. `Required` `Filter(multi eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Project

The project for which this risk applies. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Projects](Projects.Classic.Projects.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ResponsiblePerson

The person who is responsible for handling the risk. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
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

