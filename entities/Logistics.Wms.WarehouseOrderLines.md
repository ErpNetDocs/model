---
uid: Logistics.Wms.WarehouseOrderLines
---
# Logistics.Wms.WarehouseOrderLines


A planned task (operation) in a warehouse order.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseOrderLines  
Base Table: Wms_Warehouse_Order_Lines  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {WarehouseOrder.DocumentNo} {WarehouseOrder.DocumentType.TypeName:T}  
Search Members: WarehouseOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.WarehouseOrders](Logistics.Wms.WarehouseOrders.md)  
Aggregate Root:  
[Logistics.Wms.WarehouseOrders](Logistics.Wms.WarehouseOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Wms.WarehouseOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineGroupNo](Logistics.Wms.WarehouseOrderLines.md#linegroupno) | int32 | Line group number. Indicates which lines are part of the same group e.g. group of components of the same composite product.[Required] [Default(1)] [Filter(eq;ge;le)] [Introduced in version 23.1.0.67] 
| [LineNo](Logistics.Wms.WarehouseOrderLines.md#lineno) | int32 | Unique consecutive line number within the order.[Required] [Filter(eq)] 
| [Notes](Logistics.Wms.WarehouseOrderLines.md#notes) | string (max) __nullable__ | Notes for this WarehouseOrderLine. 
| [ParentLineNo](Logistics.Wms.WarehouseOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute another line.[Filter(multi eq)] [Introduced in version 22.1.4.26] 
| [Quantity](Logistics.Wms.WarehouseOrderLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the product, which should be operated.[Unit: QuantityUnit] [Required] [Default(0)] [Filter(eq;ge;le)] 
| [QuantityBase](Logistics.Wms.WarehouseOrderLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Filter(multi eq;ge;le)] [Introduced in version 22.1.4.41] 
| [StandardQuantity](Logistics.Wms.WarehouseOrderLines.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Introduced in version 22.1.4.42] 
| [TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype) | [TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype) | The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble.[Required] [Filter(multi eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Wms.WarehouseOrderLines.md#document) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | The owner document. The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` |
| [LogisticUnit](Logistics.Wms.WarehouseOrderLines.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | Logistic unit, which should be used in the operation. |
| [Lot](Logistics.Wms.WarehouseOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product, which should be operated. NULL for operations, which are not lot-specific, or when any lot can be used. |
| [ParentDocument](Logistics.Wms.WarehouseOrderLines.md#parentdocument) | [WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. |
| [Product](Logistics.Wms.WarehouseOrderLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which should be operated. |
| [ProductVariant](Logistics.Wms.WarehouseOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which should be used. |
| [QuantityUnit](Logistics.Wms.WarehouseOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of Quantity. |
| [SerialNumber](Logistics.Wms.WarehouseOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [ToWarehouseLocation](Logistics.Wms.WarehouseOrderLines.md#towarehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable) | Destination warehouse location. NULL for operations, which do not specify destination location. |
| [WarehouseLocation](Logistics.Wms.WarehouseOrderLines.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable) | Location, where the opeartion should be performed. NULL for operations, which do not require location. |
| [WarehouseOrder](Logistics.Wms.WarehouseOrderLines.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [WarehouseWorker](Logistics.Wms.WarehouseOrderLines.md#warehouseworker) | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable) | The human or robot worker, which should execute the line. NULL means that the line is shared among all workers, assigned to the order. |
| [WarehouseZone](Logistics.Wms.WarehouseOrderLines.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | The warehouse zone, in which the operation should be performed. NULL for operations which do not require specific zone. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehouseOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineGroupNo

Line group number. Indicates which lines are part of the same group e.g. group of components of the same composite product.[Required] [Default(1)] [Filter(eq;ge;le)] [Introduced in version 23.1.0.67]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **HiddenByDefault**  

### LineNo

Unique consecutive line number within the order.[Required] [Filter(eq)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WarehouseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.WarehouseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this WarehouseOrderLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line.[Filter(multi eq)] [Introduced in version 22.1.4.26]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity of the product, which should be operated.[Unit: QuantityUnit] [Required] [Default(0)] [Filter(eq;ge;le)]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Filter(multi eq;ge;le)] [Introduced in version 22.1.4.41]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantity

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Introduced in version 22.1.4.42]

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TaskType

The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble.[Required] [Filter(multi eq)]

Type: **[TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype)**  
Category: **System**  
Allowed values for the `TaskType`(Logistics.Wms.WarehouseOrderLines.md#tasktype) data attribute  
Allowed Values (Logistics.Wms.WarehouseOrderLinesRepository.TaskType Enum Members)  

| Value | Description |
| ---- | --- |
| Receive | Receive value. Stored as 'REC'. <br /> Database Value: 'REC' <br /> Model Value: 0 <br /> Domain API Value: 'Receive' |
| Dispatch | Dispatch value. Stored as 'DIS'. <br /> Database Value: 'DIS' <br /> Model Value: 1 <br /> Domain API Value: 'Dispatch' |
| Move | Move value. Stored as 'MOV'. <br /> Database Value: 'MOV' <br /> Model Value: 2 <br /> Domain API Value: 'Move' |
| Label | Label value. Stored as 'LBL'. <br /> Database Value: 'LBL' <br /> Model Value: 3 <br /> Domain API Value: 'Label' |
| Inspect | Inspect value. Stored as 'INS'. <br /> Database Value: 'INS' <br /> Model Value: 4 <br /> Domain API Value: 'Inspect' |
| Pack | Pack value. Stored as 'PCK'. <br /> Database Value: 'PCK' <br /> Model Value: 5 <br /> Domain API Value: 'Pack' |
| Unpack | Unpack value. Stored as 'UPK'. <br /> Database Value: 'UPK' <br /> Model Value: 6 <br /> Domain API Value: 'Unpack' |
| Kit | Kit value. Stored as 'KIT'. <br /> Database Value: 'KIT' <br /> Model Value: 7 <br /> Domain API Value: 'Kit' |
| Dekit | Dekit value. Stored as 'DKT'. <br /> Database Value: 'DKT' <br /> Model Value: 8 <br /> Domain API Value: 'Dekit' |
| Count | Count value. Stored as 'CNT'. <br /> Database Value: 'CNT' <br /> Model Value: 9 <br /> Domain API Value: 'Count' |
| UserTask | UserTask value. Stored as 'TSK'. <br /> Database Value: 'TSK' <br /> Model Value: 10 <br /> Domain API Value: 'UserTask' |
| ComponentDispatch | ComponentDispatch value. Stored as 'CDP'. <br /> Database Value: 'CDP' <br /> Model Value: 11 <br /> Domain API Value: 'ComponentDispatch' |
| ComponentReceive | ComponentReceive value. Stored as 'CRC'. <br /> Database Value: 'CRC' <br /> Model Value: 12 <br /> Domain API Value: 'ComponentReceive' |
| Assemble | Assemble value. Stored as 'ASM'. <br /> Database Value: 'ASM' <br /> Model Value: 13 <br /> Domain API Value: 'Assemble' |
| Disassemble | Disassemble value. Stored as 'DSM'. <br /> Database Value: 'DSM' <br /> Model Value: 14 <br /> Domain API Value: 'Disassemble' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.WarehouseOrder.TaskType`

Front-End Recalc Expressions:  
`obj.WarehouseOrder.TaskType`
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

The owner document. The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LogisticUnit

Logistic unit, which should be used in the operation.

Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Lot

The lot of the product, which should be operated. NULL for operations, which are not lot-specific, or when any lot can be used.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line.

Type: **[WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product, which should be operated.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The product variant, which should be used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ToWarehouseLocation

Destination warehouse location. NULL for operations, which do not specify destination location.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WarehouseLocation

Location, where the opeartion should be performed. NULL for operations, which do not require location.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WarehouseOrder

The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WarehouseWorker

The human or robot worker, which should execute the line. NULL means that the line is shared among all workers, assigned to the order.

Type: **[WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.WarehouseOrder.WarehouseWorker`

Front-End Recalc Expressions:  
`obj.WarehouseOrder.WarehouseWorker`
### WarehouseZone

The warehouse zone, in which the operation should be performed. NULL for operations which do not require specific zone.

Type: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.WarehouseLocation != null), obj.WarehouseLocation.WarehouseZone, obj.WarehouseZone)`

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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseOrderLines

Domain API Entity Type: 
Logistics_Wms_WarehouseOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseOrderLines?$top=10>

