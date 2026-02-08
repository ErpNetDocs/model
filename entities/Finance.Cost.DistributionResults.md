---
uid: Finance.Cost.DistributionResults
---
# Finance.Cost.DistributionResults


Contains the results of a cost distribution calculation.

## General
Namespace: [Finance.Cost](Finance.Cost.md)  
Repository: Finance.Cost.DistributionResults  
Base Table: Cost_Distribution_Results  
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
| [DistributedAmountBase](Finance.Cost.DistributionResults.md#distributedamountbase) | [Amount (14, 5)](../data-types.md#amount) | The amount (in base currency) of the distributed cost. The amount is calculated for the combination of output and cost type.`Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required` 
| [LineNo](Finance.Cost.DistributionResults.md#lineno) | int32 | Consecutive line number (within the cost distribution document) of the result.`Required` 
| [OutputLineNo](Finance.Cost.DistributionResults.md#outputlineno) | int32 | The line number (within the document) of the output over which the cost is distributed.`Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostDistribution](Finance.Cost.DistributionResults.md#costdistribution) | [Distributions](Finance.Cost.Distributions.md) | The <see cref="Distribution"/> to which this DistributionResult belongs. `Required` `Filter(multi eq)` `Owner` |
| [CostType](Finance.Cost.DistributionResults.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The cost type for which the current distribution is calculated. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Cost.DistributionResults.md#id) | guid |  
| [ObjectVersion](Finance.Cost.DistributionResults.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Cost.DistributionResults.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DistributedAmountBase

The amount (in base currency) of the distributed cost. The amount is calculated for the combination of output and cost type.`Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required`

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number (within the cost distribution document) of the result.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.CostDistribution.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.CostDistribution.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### OutputLineNo

The line number (within the document) of the output over which the cost is distributed.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### CostDistribution

The <see cref="Distribution"/> to which this DistributionResult belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Distributions](Finance.Cost.Distributions.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### CostType

The cost type for which the current distribution is calculated.

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

[!list limit=1000 erp.entity=Finance.Cost.DistributionResults erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.DistributionResults erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Cost_DistributionResults

Domain API Entity Type: 
Finance_Cost_DistributionResult

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Cost_DistributionResults?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Cost_DistributionResults?$top=10>

