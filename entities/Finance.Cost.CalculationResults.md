---
uid: Finance.Cost.CalculationResults
---
# Finance.Cost.CalculationResults


Contains the results of cost calculations.

## General
Namespace: [Finance.Cost](Finance.Cost.md)  
Repository: Finance.Cost.CalculationResults  
Base Table: Cost_Calculation_Results  
API access:  ReadWrite  

## Visualization
Display Format: {Calculation.EntityName}  
Search Members: Calculation.EntityName  
Name Member: Calculation.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  
Aggregate Root:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FullCost](Finance.Cost.CalculationResults.md#fullcost) | decimal (14, 2) | The full cost of the specified quantity[Required] [Default(0)] 
| [LineNo](Finance.Cost.CalculationResults.md#lineno) | int32 | Consecutive number of the line within the calculation[Required] 
| [ProjectId](Finance.Cost.CalculationResults.md#projectid) | guid __nullable__ | The Project to which the cost was allocated. When null, the cost was not allocated to any specific Project. `Filter(multi eq)` 
| [Quantity](Finance.Cost.CalculationResults.md#quantity) | decimal (14, 3) | The quantity of the product[Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Calculation](Finance.Cost.CalculationResults.md#calculation) | [Calculations](Finance.Cost.Calculations.md) | The <see cref="Calculation"/> to which this CalculationResult belongs. `Required` `Filter(multi eq)` `Owner` |
| [Lot](Finance.Cost.CalculationResults.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot to which the cost was allocated. When NULL, the cost was not allocated to any specific Lot. |
| [Product](Finance.Cost.CalculationResults.md#product) | [Products](General.Products.Products.md) | The Product to which the cost was allocated. When NULL, the cost was not allocated to any specific Product. |
| [ProfitCenter](Finance.Cost.CalculationResults.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | The Profit Center to which the cost was allocated. When NULL, the cost was not allocated to any specific Profit Center. |
| [SalesOrder](Finance.Cost.CalculationResults.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | The Sales Order to which the cost was allocated. When NULL, the cost was not allocated to any specific Sales Order. |
| [Workgroup](Finance.Cost.CalculationResults.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) (nullable) | The Workgroup to which the cost was allocated. When NULL, the cost was not allocated to any specific Workgroup. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Cost.CalculationResults.md#id) | guid |  
| [ObjectVersion](Finance.Cost.CalculationResults.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Cost.CalculationResults.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FullCost

The full cost of the specified quantity[Required] [Default(0)]

Type: **decimal (14, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive number of the line within the calculation[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Calculation.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Calculation.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ProjectId

The Project to which the cost was allocated. When null, the cost was not allocated to any specific Project. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity of the product[Required] [Default(0)]

Type: **decimal (14, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

### Calculation

The <see cref="Calculation"/> to which this CalculationResult belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Calculations](Finance.Cost.Calculations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Lot

The Lot to which the cost was allocated. When NULL, the cost was not allocated to any specific Lot.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The Product to which the cost was allocated. When NULL, the cost was not allocated to any specific Product.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProfitCenter

The Profit Center to which the cost was allocated. When NULL, the cost was not allocated to any specific Profit Center.

Type: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesOrder

The Sales Order to which the cost was allocated. When NULL, the cost was not allocated to any specific Sales Order.

Type: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Workgroup

The Workgroup to which the cost was allocated. When NULL, the cost was not allocated to any specific Workgroup.

Type: **[Workgroups](Production.Resources.Workgroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Cost.CalculationResults erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.CalculationResults erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Cost_CalculationResults

Domain API Entity Type: 
Finance_Cost_CalculationResult

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Cost_CalculationResults?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Cost_CalculationResults?$top=10>

