---
uid: Finance.Cost.CalculationProductOutputs
---
# Finance.Cost.CalculationProductOutputs Entity

**Namespace:** [Finance.Cost](Finance.Cost.md)  

Represents costs allocated to product outputs. Entity: Cost_Calculation_Product_Outputs

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
| [DisplayText](Finance.Cost.CalculationProductOutputs.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Cost.CalculationProductOutputs.md#id) | guid |  
| [LineNo](Finance.Cost.CalculationProductOutputs.md#lineno) | int32 | Consecutive number of the line within the calculation. `Required` 
| [ObjectVersion](Finance.Cost.CalculationProductOutputs.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProjectId](Finance.Cost.CalculationProductOutputs.md#projectid) | guid __nullable__ | The Project, which absorbed the cost. `Filter(multi eq)` 
| [Quantity](Finance.Cost.CalculationProductOutputs.md#quantity) | decimal (18, 3) | The quantity produced. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Calculation](Finance.Cost.CalculationProductOutputs.md#calculation) | [Calculations](Finance.Cost.Calculations.md) | The <see cref="Calculation"/> to which this CalculationProductOutput belongs. `Required` `Filter(multi eq)` `Owner` |
| [Lot](Finance.Cost.CalculationProductOutputs.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot, which absorbed the cost. `Filter(multi eq)` |
| [Parent](Finance.Cost.CalculationProductOutputs.md#parent) | [CalculationProductOutputs](Finance.Cost.CalculationProductOutputs.md) (nullable) | When not null specifies the parent output, whose cost is "absorbed" within the current output. `Filter(multi eq)` |
| [Product](Finance.Cost.CalculationProductOutputs.md#product) | [Products](General.Products.Products.md) | The Product, which absorbed the cost. `Required` `Filter(multi eq)` |
| [ProfitCenter](Finance.Cost.CalculationProductOutputs.md#profitcenter) | [ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable) | The Profit Center, which absorbed the cost. `Filter(multi eq)` |
| [SalesOrder](Finance.Cost.CalculationProductOutputs.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | The Sales Order, which absorbed the cost. `Filter(multi eq)` |
| [Workgroup](Finance.Cost.CalculationProductOutputs.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) (nullable) | The Workgroup, which absorbed the cost. `Filter(multi eq)` |
| [WorkOrder](Finance.Cost.CalculationProductOutputs.md#workorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) (nullable) | The Work Order, which absorbed the cost. `Filter(multi eq)` |


## Attribute Details

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

### LineNo

Consecutive number of the line within the calculation. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Calculation.ProductOutputs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.Calculation.ProductOutputs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProjectId

The Project, which absorbed the cost. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity produced. `Required` `Default(0)`

_Type_: **decimal (18, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Calculation

The <see cref="Calculation"/> to which this CalculationProductOutput belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Calculations](Finance.Cost.Calculations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Lot

The Lot, which absorbed the cost. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Parent

When not null specifies the parent output, whose cost is "absorbed" within the current output. `Filter(multi eq)`

_Type_: **[CalculationProductOutputs](Finance.Cost.CalculationProductOutputs.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The Product, which absorbed the cost. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProfitCenter

The Profit Center, which absorbed the cost. `Filter(multi eq)`

_Type_: **[ProfitCenters](Finance.Accounting.ProfitCenters.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesOrder

The Sales Order, which absorbed the cost. `Filter(multi eq)`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Workgroup

The Workgroup, which absorbed the cost. `Filter(multi eq)`

_Type_: **[Workgroups](Production.Resources.Workgroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkOrder

The Work Order, which absorbed the cost. `Filter(multi eq)`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Cost.CalculationProductOutputs erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.CalculationProductOutputs erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_CalculationProductOutputs?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_CalculationProductOutputs?$top=10>

