---
uid: Projects.ProjectRisks
---
# Projects.ProjectRisks Entity

**Namespace:** [Projects](Projects.md)  

Contains risks, associated to projects. Entity: Prj_Project_Risks

## Default Visualization
Default Display Text Format:  
_{RiskName}_  
Default Search Members:  
_RiskName_  
Name Data Member:  
_RiskName_  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Projects](Projects.Projects.md)  
Aggregate Root:  
[Projects.Projects](Projects.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreateDate](Projects.ProjectRisks.md#createdate) | date | The creation date of the project risk. `Required` `Default(Now)` `Filter(eq)` 
| [Description](Projects.ProjectRisks.md#description) | string (max) __nullable__ | The description of this ProjectRisk. `Filter(like)` 
| [DisplayText](Projects.ProjectRisks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.ProjectRisks.md#id) | guid |  
| [ImpactPercent](Projects.ProjectRisks.md#impactpercent) | decimal (3, 2) | The impact of the risk to the project, expressed as percentage of the total project value. `Required` `Default(0)` 
| [ObjectVersion](Projects.ProjectRisks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProbabilityPercent](Projects.ProjectRisks.md#probabilitypercent) | decimal (3, 2) | The probability of the risk occurring. `Required` `Default(0)` 
| [ResolutionStrategy](Projects.ProjectRisks.md#resolutionstrategy) | string (max) __nullable__ | The strategy chosen to handle the risk. `Filter(eq)` 
| [Resolved](Projects.ProjectRisks.md#resolved) | boolean | True if the risk is resolved. `Required` `Default(false)` `Filter(eq)` 
| [ResolveDate](Projects.ProjectRisks.md#resolvedate) | date __nullable__ | The date on which the risk is resolved. `Filter(eq)` 
| [RiskName](Projects.ProjectRisks.md#riskname) | string (254) | The short name of the risk. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Project](Projects.ProjectRisks.md#project) | [Projects](Projects.Projects.md) | The project for which this risk applies. `Required` `Filter(multi eq)` `Owner` |
| [ResponsiblePerson](Projects.ProjectRisks.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | The person who is responsible for handling the risk. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Discussion | [ProjectRiskDiscussion](Projects.ProjectRiskDiscussion.md) | List of `ProjectRiskDiscussion`(Projects.ProjectRiskDiscussion.md) child objects, based on the `Projects.ProjectRiskDiscussion.ProjectRisk`(Projects.ProjectRiskDiscussion.md#projectrisk) back reference 


## Attribute Details

### CreateDate

The creation date of the project risk. `Required` `Default(Now)` `Filter(eq)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals**  
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
_Supported Filters_: **Equals, EqualsIn**  
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

The date on which the risk is resolved. `Filter(eq)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
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

_Type_: **[Projects](Projects.Projects.md)**  
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
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Projects.ProjectRisks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.ProjectRisks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_ProjectRisks?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_ProjectRisks?$top=10>

