---
uid: Production.ShopFloor.OutputOrderConsumptionLines
---
# Production.ShopFloor.OutputOrderConsumptionLines


The internal production consumption of materials. Used only for control purposes - for comparison with the active consumption orders. Warehouse and accounting are still updated only by Consumption Orders

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.OutputOrderConsumptionLines  
Base Table: Prd_Output_Order_Consumption_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {OutputOrder.DocumentNo} {OutputOrder.DocumentType.TypeName:T}  
Search Members: OutputOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  
Aggregate Root:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantityForRun](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforrun) | [Quantity (18, 3)](../data-types.md#quantity) | The consumed quantity of the material for the operation.[Unit: QuantityUnit] [Required] [Default(0)] 
| [ConsumedQuantityForScrap](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforscrap) | [Quantity (18, 3)](../data-types.md#quantity) | The scrapped quantity of the material for this operation.[Unit: QuantityUnit] [Required] [Default(0)] 
| [ConsumedQuantityForSetup](Production.ShopFloor.OutputOrderConsumptionLines.md#consumedquantityforsetup) | [Quantity (18, 3)](../data-types.md#quantity) | The consumed quantity of the material while setting up the operation.[Unit: QuantityUnit] [Required] [Default(0)] 
| [LineNo](Production.ShopFloor.OutputOrderConsumptionLines.md#lineno) | int32 | Line number, unique within the OutputOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the OutputOrder (in order to allow insertions with adjustment documents). `Required` 
| [Notes](Production.ShopFloor.OutputOrderConsumptionLines.md#notes) | string (max) __nullable__ | Notes for this OutputOrderConsumptionLine. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.OutputOrderConsumptionLines.md#document) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The owner document. The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` |
| [LineWorkOrder](Production.ShopFloor.OutputOrderConsumptionLines.md#lineworkorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | Work order for the line. Initially copied from the header (if there work order is not null) |
| [Material](Production.ShopFloor.OutputOrderConsumptionLines.md#material) | [Products](General.Products.Products.md) | The consumed material |
| [OutputOrder](Production.ShopFloor.OutputOrderConsumptionLines.md#outputorder) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [QuantityUnit](Production.ShopFloor.OutputOrderConsumptionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit for the consumed quantity for setup, run and scrap. |
| [ScrapType](Production.ShopFloor.OutputOrderConsumptionLines.md#scraptype) | [ScrapTypes](Logistics.Inventory.ScrapTypes.md) (nullable) | When Consumed_Quantity_<br />For_Scrap <> 0 denotes the reason for the scrap |
| [WorkOrderItem](Production.ShopFloor.OutputOrderConsumptionLines.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item, for which the consumption is recorded. |
| [WorkOrderItemOperation](Production.ShopFloor.OutputOrderConsumptionLines.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable) | The operation in which the material was consumed. NULL = unknown |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.OutputOrderConsumptionLines.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.OutputOrderConsumptionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.OutputOrderConsumptionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConsumedQuantityForRun

The consumed quantity of the material for the operation.[Unit: QuantityUnit] [Required] [Default(0)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ConsumedQuantityForScrap

The scrapped quantity of the material for this operation.[Unit: QuantityUnit] [Required] [Default(0)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ConsumedQuantityForSetup

The consumed quantity of the material while setting up the operation.[Unit: QuantityUnit] [Required] [Default(0)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineNo

Line number, unique within the OutputOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the OutputOrder (in order to allow insertions with adjustment documents). `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.OutputOrder.ConsumptionLines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.OutputOrder.ConsumptionLines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this OutputOrderConsumptionLine.

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

### Document

The owner document. The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)`

Type: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineWorkOrder

Work order for the line. Initially copied from the header (if there work order is not null)

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.OutputOrder.WorkOrder`
### Material

The consumed material

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OutputOrder

The <see cref="OutputOrder"/> to which this OutputOrderConsumptionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit for the consumed quantity for setup, run and scrap.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Material.MeasurementUnit`
### ScrapType

When Consumed_Quantity_For_Scrap <> 0 denotes the reason for the scrap

Type: **[ScrapTypes](Logistics.Inventory.ScrapTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkOrderItem

The work order item, for which the consumption is recorded.

Type: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkOrderItemOperation

The operation in which the material was consumed. NULL = unknown

Type: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable)**  
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

