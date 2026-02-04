---
uid: Production.ShopFloor.ConsumptionOrderLines
---
# Production.ShopFloor.ConsumptionOrderLines


Detail lines of orders for material consumption.

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.ConsumptionOrderLines  
Base Table: Prd_Consumption_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineOrd}. {ConsumptionOrder.DocumentNo} {ConsumptionOrder.DocumentType.TypeName:T}  
Search Members: ConsumptionOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  
Aggregate Root:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantity](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Consumed quantity in the operation. 
| [ConsumedQuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The requested quantity equivalence in the base measurement category of the requested material. 
| [ConsumedStandard<br />QuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Quantity using the measurement ratios. 
| [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient). 
| [CurrentBalanceBase](Production.ShopFloor.ConsumptionOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineOrd](Production.ShopFloor.ConsumptionOrderLines.md#lineord) | int32 | Non-unique line number within the order 
| [Notes](Production.ShopFloor.ConsumptionOrderLines.md#notes) | string (max) __nullable__ | Notes for this ConsumptionOrderLine. 
| [ScheduledDateTime](Production.ShopFloor.ConsumptionOrderLines.md#scheduleddatetime) | datetime __nullable__ | The scheduled date, when the material is needed. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantityUnit](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Measurement unit of the consumed quantity in the operation. |
| [ConsumptionOrder](Production.ShopFloor.ConsumptionOrderLines.md#consumptionorder) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Production.ShopFloor.ConsumptionOrderLines.md#document) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The owner document. The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.ConsumptionOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Lot from which to get the material. If not specified (default) - Any lot can be used. |
| [Product](Production.ShopFloor.ConsumptionOrderLines.md#product) | [Products](General.Products.Products.md) | The requested material. |
| [SerialNumber](Production.ShopFloor.ConsumptionOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [Store](Production.ShopFloor.ConsumptionOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store, from which the material is requested. |
| [StoreBin](Production.ShopFloor.ConsumptionOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | If not NULL, specifies that the material has to be consumed from specific store bin |
| [WorkOrderItemIngredient](Production.ShopFloor.ConsumptionOrderLines.md#workorderitemingredient) | [WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md) | The Work Order Item Ingredient for which we are ordering materials. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.ConsumptionOrderLines.md#id) | guid | Unique order lline Id 
| [ObjectVersion](Production.ShopFloor.ConsumptionOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.ConsumptionOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConsumedQuantity

Consumed quantity in the operation.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ConsumedQuantityUnit == null), null, IIF( ( obj.WorkOrderItemIngredient != null), obj.WorkOrderItemIngredient.GetSumConsumedQuantity( obj.ConsumedQuantityUnit), obj.ConsumedQuantity))`
### ConsumedQuantityBase

The requested quantity equivalence in the base measurement category of the requested material.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Quantity using the measurement ratios.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumptionType

Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient).

Type: **[ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype)**  
Category: **System**  
Allowed values for the `ConsumptionType`(Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) data attribute  
Allowed Values (Production.ShopFloor.ConsumptionOrderLinesRepository.ConsumptionType Enum Members)  

| Value | Description |
| ---- | --- |
| ForSpecifiedItem | ForSpecifiedItem value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'ForSpecifiedItem' |
| ForAllItems | ForAllItems value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 1 <br /> Domain API Value: 'ForAllItems' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.WorkOrderItemIngredient != null) AndAlso ( obj.WorkOrderItemIngredient.WorkOrderItem != null)), ForSpecifiedItem, ForAllItems)`
### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineOrd

Non-unique line number within the order

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ConsumptionOrderLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ScheduledDateTime

The scheduled date, when the material is needed.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Id

Unique order lline Id

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

### ConsumedQuantityUnit

Measurement unit of the consumed quantity in the operation.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### ConsumptionOrder

The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

Lot from which to get the material. If not specified (default) - Any lot can be used.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The requested material.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.WorkOrderItemIngredient.Material`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Store

The store, from which the material is requested.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.ConsumptionOrder.Store`

Front-End Recalc Expressions:  
`obj.ConsumptionOrder.Store`
### StoreBin

If not NULL, specifies that the material has to be consumed from specific store bin

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WorkOrderItemIngredient

The Work Order Item Ingredient for which we are ordering materials.

Type: **[WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_ConsumptionOrderLines

Domain API Entity Type: 
Production_ShopFloor_ConsumptionOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_ConsumptionOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_ConsumptionOrderLines?$top=10>

