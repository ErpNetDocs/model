---
uid: Finance.Cost.DistributionCosts
---
# Finance.Cost.DistributionCosts


The cost types and their amounts which are distributed by a Cost Distribution document.

## General
Namespace: [Finance.Cost](Finance.Cost.md)  
Repository: Finance.Cost.DistributionCosts  
Base Table: Cost_Distribution_Costs  
API access:  ReadWrite  

## Visualization
Display Format: {CostDistribution.EntityName}  
Search Members: CostDistribution.EntityName  
Name Member: CostDistribution.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Distributions](Finance.Cost.Distributions.md)  
Aggregate Root:  
[Finance.Cost.Distributions](Finance.Cost.Distributions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountBase](Finance.Cost.DistributionCosts.md#amountbase) | [Amount (12, 2)](../data-types.md#amount) | The cost (in base currency) which should be distributed.`Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq)` 
| [Notes](Finance.Cost.DistributionCosts.md#notes) | string (max) __nullable__ | Notes for this DistributionCost. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostDistribution](Finance.Cost.DistributionCosts.md#costdistribution) | [Distributions](Finance.Cost.Distributions.md) | The <see cref="Distribution"/> to which this DistributionCost belongs. `Required` `Filter(multi eq)` `Owner` |
| [CostType](Finance.Cost.DistributionCosts.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The type of the cost, which will be distributed. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Cost.DistributionCosts.md#id) | guid |  
| [ObjectVersion](Finance.Cost.DistributionCosts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Cost.DistributionCosts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AmountBase

The cost (in base currency) which should be distributed.`Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required` `Filter(eq)`

Type: **[Amount (12, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this DistributionCost.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### CostDistribution

The <see cref="Distribution"/> to which this DistributionCost belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Distributions](Finance.Cost.Distributions.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### CostType

The type of the cost, which will be distributed.

Type: **[CostTypes](Finance.Cost.CostTypes.md)**  
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

[!list limit=1000 erp.entity=Finance.Cost.DistributionCosts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.DistributionCosts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Cost_DistributionCosts

Domain API Entity Type: 
Finance_Cost_DistributionCost

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Cost_DistributionCosts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Cost_DistributionCosts?$top=10>

