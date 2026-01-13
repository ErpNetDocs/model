---
uid: Finance.Cost.CalculationResults
---
# Finance.Cost.CalculationResults Entity

**Namespace:** [Finance.Cost](Finance.Cost.md)  

Contains the results of cost calculations. Entity: Cost_Calculation_Results

## Default Visualization
Default Display Text Format:  
_{Calculation.EntityName}_  
Default Search Members:  
_Calculation.EntityName_  
Name Data Member:  
_Calculation.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  
Aggregate Root:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Finance.Cost.CalculationResults.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FullCost](Finance.Cost.CalculationResults.md#fullcost) | decimal (14, 2) | The full cost of the specified quantity. `Required` `Default(0)` 
| [Id](Finance.Cost.CalculationResults.md#id) | guid |  
| [LineNo](Finance.Cost.CalculationResults.md#lineno) | int32 | Consecutive number of the line within the calculation. `Required` 
| [ObjectVersion](Finance.Cost.CalculationResults.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProjectId](Finance.Cost.CalculationResults.md#projectid) | guid __nullable__ | The Project to which the cost was allocated. When null, the cost was not allocated to any specific Project. `Filter(multi eq)` 
| [Quantity](Finance.Cost.CalculationResults.md#quantity) | decimal (14, 3) | The quantity of the product. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Calculation](Finance.Cost.CalculationResults.md#calculation) | [Calculations](Finance.Cost.Calculations.md) | The <see cref="Calculation"/> to which this CalculationResult belongs. `Required` `Filter(multi eq)` `Owner` |
| [Lot](Finance.Cost.CalculationResults.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot to which the cost was allocated. When null, the cost was not allocated to any specific Lot. `Filter(multi eq)` |
| [Product](Finance.Cost.CalculationResults.md#product) | [Products](General.Products.Products.md) | The Product to which the cost was allocated. When null, the cost was not allocated to any specific Product. `Required` `Filter(multi eq)` |
| [ProfitCenter](Finance.Cost.CalculationResults.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | The Profit Center to which the cost was allocated. When null, the cost was not allocated to any specific Profit Center. `Filter(multi eq)` |
| [SalesOrder](Finance.Cost.CalculationResults.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | The Sales Order to which the cost was allocated. When null, the cost was not allocated to any specific Sales Order. `Filter(multi eq)` |
| [Workgroup](Finance.Cost.CalculationResults.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) (nullable) | The Workgroup to which the cost was allocated. When null, the cost was not allocated to any specific Workgroup. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FullCost

The full cost of the specified quantity. `Required` `Default(0)`

_Type_: **decimal (14, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive number of the line within the calculation. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Calculation.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.Calculation.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProjectId

The Project to which the cost was allocated. When null, the cost was not allocated to any specific Project. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity of the product. `Required` `Default(0)`

_Type_: **decimal (14, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Calculation

The <see cref="Calculation"/> to which this CalculationResult belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Calculations](Finance.Cost.Calculations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Lot

The Lot to which the cost was allocated. When null, the cost was not allocated to any specific Lot. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The Product to which the cost was allocated. When null, the cost was not allocated to any specific Product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

The Profit Center to which the cost was allocated. When null, the cost was not allocated to any specific Profit Center. `Filter(multi eq)`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesOrder

The Sales Order to which the cost was allocated. When null, the cost was not allocated to any specific Sales Order. `Filter(multi eq)`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Workgroup

The Workgroup to which the cost was allocated. When null, the cost was not allocated to any specific Workgroup. `Filter(multi eq)`

_Type_: **[Workgroups](Production.Resources.Workgroups.md) (nullable)**  
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

