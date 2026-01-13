---
uid: Production.ShopFloor.OutputOrderConsumptionLines
---
# Production.ShopFloor.OutputOrderConsumptionLines Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

The internal production consumption of materials. Used only for control purposes - for comparison with the active consumption orders. Warehouse and accounting are still updated only by Consumption Orders. Entity: Prd_Output_Order_Consumption_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {OutputOrder.DocumentNo} {OutputOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_OutputOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  
Aggregate Root:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantityForRun](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforrun) | [Quantity (18, 3)](../data-types.md#quantity) | The consumed quantity of the material for the operation. `Unit: QuantityUnit` `Required` `Default(0)` 
| [ConsumedQuantityForScrap](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforscrap) | [Quantity (18, 3)](../data-types.md#quantity) | The scrapped quantity of the material for this operation. `Unit: QuantityUnit` `Required` `Default(0)` 
| [ConsumedQuantityForSetup](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforsetup) | [Quantity (18, 3)](../data-types.md#quantity) | The consumed quantity of the material while setting up the operation. `Unit: QuantityUnit` `Required` `Default(0)` 
| [DisplayText](Production.ShopFloor.OutputOrderConsumptionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.OutputOrderConsumptionLines.md#id) | guid |  
| [LineNo](Production.ShopFloor.OutputOrderConsumptionLines.md#lineno) | int32 | Line number, unique within the OutputOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the OutputOrder (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Production.ShopFloor.OutputOrderConsumptionLines.md#notes) | string (max) __nullable__ | Notes for this OutputOrderConsumptionLine. 
| [ObjectVersion](Production.ShopFloor.OutputOrderConsumptionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.OutputOrderConsumptionLines.md#document) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The owner document. The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` |
| [LineWorkOrder](Production.ShopFloor.OutputOrderConsumptionLines.md#lineworkorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | Work order for the line. Initially copied from the header (if there work order is not null). `Required` `Filter(multi eq)` |
| [Material](Production.ShopFloor.OutputOrderConsumptionLines.md#material) | [Products](General.Products.Products.md) | The consumed material. `Required` `Filter(multi eq)` |
| [OutputOrder](Production.ShopFloor.OutputOrderConsumptionLines.md#outputorder) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [QuantityUnit](Production.ShopFloor.OutputOrderConsumptionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit for the consumed quantity for setup, run and scrap. `Required` `Filter(multi eq)` |
| [ScrapType](Production.ShopFloor.OutputOrderConsumptionLines.md#scraptype) | [ScrapTypes](Logistics.Inventory.ScrapTypes.md) (nullable) | When Consumed_Quantity_<br />For_Scrap &lt;&gt; 0 denotes the reason for the scrap. `Filter(multi eq)` |
| [WorkOrderItem](Production.ShopFloor.OutputOrderConsumptionLines.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item, for which the consumption is recorded. `Required` `Filter(multi eq)` |
| [WorkOrderItemOperation](Production.ShopFloor.OutputOrderConsumptionLines.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable) | The operation in which the material was consumed. null = unknown. `Filter(multi eq)` |


## Attribute Details

### ConsumedQuantityForRun

The consumed quantity of the material for the operation. `Unit: QuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ConsumedQuantityForScrap

The scrapped quantity of the material for this operation. `Unit: QuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ConsumedQuantityForSetup

The consumed quantity of the material while setting up the operation. `Unit: QuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
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

### LineNo

Line number, unique within the OutputOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the OutputOrder (in order to allow insertions with adjustment documents). `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.OutputOrder.ConsumptionLines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.OutputOrder.ConsumptionLines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this OutputOrderConsumptionLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)`

_Type_: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LineWorkOrder

Work order for the line. Initially copied from the header (if there work order is not null). `Required` `Filter(multi eq)`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.OutputOrder.WorkOrder`
### Material

The consumed material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OutputOrder

The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit for the consumed quantity for setup, run and scrap. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Material.MeasurementUnit`
### ScrapType

When Consumed_Quantity_For_Scrap &lt;&gt; 0 denotes the reason for the scrap. `Filter(multi eq)`

_Type_: **[ScrapTypes](Logistics.Inventory.ScrapTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkOrderItem

The work order item, for which the consumption is recorded. `Required` `Filter(multi eq)`

_Type_: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkOrderItemOperation

The operation in which the material was consumed. null = unknown. `Filter(multi eq)`

_Type_: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderConsumptionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderConsumptionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_OutputOrderConsumptionLines

Domain API Entity Type: 
Production_ShopFloor_OutputOrderConsumptionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_OutputOrderConsumptionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_OutputOrderConsumptionLines?$top=10>

