---
uid: Projects.Classic.TemplateRisks
---
# Projects.Classic.TemplateRisks


Contains project risks, which will be copied to projects, based on the template.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.TemplateRisks  
Base Table: Prj_Template_Risks  
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
[Projects.Classic.Templates](Projects.Classic.Templates.md)  
Aggregate Root:  
[Projects.Classic.Templates](Projects.Classic.Templates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Projects.Classic.TemplateRisks.md#description) | string (max) __nullable__ | The description of this TemplateRisk. 
| [ImpactPercent](Projects.Classic.TemplateRisks.md#impactpercent) | decimal (3, 2) | The impact of the risk to the project, expressed as percentage of the total project value. `Required` `Default(0)` 
| [ProbabilityPercent](Projects.Classic.TemplateRisks.md#probabilitypercent) | decimal (3, 2) | The probability of the risk occurring. `Required` `Default(0)` 
| [RiskName](Projects.Classic.TemplateRisks.md#riskname) | string (254) | The name of the risk. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTemplate](Projects.Classic.TemplateRisks.md#projecttemplate) | [Templates](Projects.Classic.Templates.md) | The <see cref="Template"/> to which this TemplateRisk belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.TemplateRisks.md#id) | guid |  
| [ObjectVersion](Projects.Classic.TemplateRisks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.TemplateRisks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Description

The description of this TemplateRisk.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ImpactPercent

The impact of the risk to the project, expressed as percentage of the total project value. `Required` `Default(0)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ProbabilityPercent

The probability of the risk occurring. `Required` `Default(0)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### RiskName

The name of the risk. `Required`

Type: **string (254)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### ProjectTemplate

The <see cref="Template"/> to which this TemplateRisk belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Templates](Projects.Classic.Templates.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Projects.Classic.TemplateRisks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.TemplateRisks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_TemplateRisks

Domain API Entity Type: 
Projects_Classic_TemplateRisk

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_TemplateRisks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_TemplateRisks?$top=10>

