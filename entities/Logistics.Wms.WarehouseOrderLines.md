---
uid: Logistics.Wms.WarehouseOrderLines
---
# Logistics.Wms.WarehouseOrderLines Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

A planned task (operation) in a warehouse order. Entity: Wms_Warehouse_Order_Lines (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {WarehouseOrder.DocumentNo} {WarehouseOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_WarehouseOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Logistics.Wms.WarehouseOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Wms.WarehouseOrderLines.md#id) | guid |  
| [LineGroupNo](Logistics.Wms.WarehouseOrderLines.md#linegroupno) | int32 | Line group number. Indicates which lines are part of the same group e.g. group of components of the same composite product. `Required` `Default(1)` `Filter(eq;ge;le)` `Introduced in version 23.1.0.67` 
| [LineNo](Logistics.Wms.WarehouseOrderLines.md#lineno) | int32 | Unique consecutive line number within the order. `Required` `Filter(eq)` 
| [Notes](Logistics.Wms.WarehouseOrderLines.md#notes) | string (max) __nullable__ | Notes for this WarehouseOrderLine. 
| [ObjectVersion](Logistics.Wms.WarehouseOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineNo](Logistics.Wms.WarehouseOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.26` 
| [Quantity](Logistics.Wms.WarehouseOrderLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the product, which should be processed. `Unit: QuantityUnit` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [QuantityBase](Logistics.Wms.WarehouseOrderLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(multi eq;ge;le)` `Introduced in version 22.1.4.41` 
| [StandardQuantity](Logistics.Wms.WarehouseOrderLines.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.4.42` 
| [TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype) | [TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype) | The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Wms.WarehouseOrderLines.md#document) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | The owner document. The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` |
| [LogisticUnit](Logistics.Wms.WarehouseOrderLines.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | Logistic unit, which should be used in the operation. `Filter(multi eq)` `Introduced in version 21.1.1.18` |
| [Lot](Logistics.Wms.WarehouseOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the product, which should be used. null for operations, which are not lot-specific, or when any lot can be used. `Filter(multi eq)` |
| [ParentDocument](Logistics.Wms.WarehouseOrderLines.md#parentdocument) | [WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.26` |
| [Product](Logistics.Wms.WarehouseOrderLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product, which should be used for the operation. `Filter(multi eq)` |
| [ProductVariant](Logistics.Wms.WarehouseOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which should be used. `Filter(multi eq)` `Introduced in version 21.1.1.18` |
| [QuantityUnit](Logistics.Wms.WarehouseOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of Quantity. null for operations, which are not quantity-related. `Filter(multi eq)` |
| [SerialNumber](Logistics.Wms.WarehouseOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the product, which should be used. null for operations, which are not serial number-specific, or when any serial number can be used. `Filter(multi eq)` |
| [ToWarehouseLocation](Logistics.Wms.WarehouseOrderLines.md#towarehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable) | Destination warehouse location. null for operations, which do not specify destination location. `Filter(multi eq)` |
| [WarehouseLocation](Logistics.Wms.WarehouseOrderLines.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable) | Location, where the opeartion should be performed. null for operations, which do not require location. `Filter(multi eq)` |
| [WarehouseOrder](Logistics.Wms.WarehouseOrderLines.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [WarehouseWorker](Logistics.Wms.WarehouseOrderLines.md#warehouseworker) | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable) | Human or robot worker, which should execute the operation. null means that the line is shared among all workers, assigned to the order. `Filter(multi eq)` |
| [WarehouseZone](Logistics.Wms.WarehouseOrderLines.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | The warehouse zone, in which the operation should be performed. null for operations which do not require specific zone. `Filter(multi eq)` |


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

_Type_: **[Quantity](../data-types.md#quantity)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### LineGroupNo

Line group number. Indicates which lines are part of the same group e.g. group of components of the same composite product. `Required` `Default(1)` `Filter(eq;ge;le)` `Introduced in version 23.1.0.67`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **HiddenByDefault**  

### LineNo

Unique consecutive line number within the order. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.WarehouseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WarehouseOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this WarehouseOrderLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.26`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity of the product, which should be processed. `Unit: QuantityUnit` `Required` `Default(0)` `Filter(eq;ge;le)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(multi eq;ge;le)` `Introduced in version 22.1.4.41`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantity

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.4.42`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantity, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TaskType

The type of the task (operation), which should be performed. REC=Receive; DIS=Dispatch; MOV=Move; LBL=Label; INS=Inspect; PCK=Pack; UPK=Unpack; KIT=Kit; DKT=Dekit; CNT=Count; TSK=User task; CDP=Component dispatch; CRC=Component receive; ASM=Assemble; DSM=Disassemble. `Required` `Filter(multi eq)`

_Type_: **[TaskType](Logistics.Wms.WarehouseOrderLines.md#tasktype)**  
_Category_: **System**  
Allowed values for the `TaskType`(Logistics.Wms.WarehouseOrderLines.md#tasktype) data attribute  
_Allowed Values (Logistics.Wms.WarehouseOrderLinesRepository.TaskType Enum Members)_  

| Value | Description |
| ---- | --- |
| Receive | Receive value. Stored as 'REC'. <br /> _Database Value:_ 'REC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Receive' |
| Dispatch | Dispatch value. Stored as 'DIS'. <br /> _Database Value:_ 'DIS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Dispatch' |
| Move | Move value. Stored as 'MOV'. <br /> _Database Value:_ 'MOV' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Move' |
| Label | Label value. Stored as 'LBL'. <br /> _Database Value:_ 'LBL' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Label' |
| Inspect | Inspect value. Stored as 'INS'. <br /> _Database Value:_ 'INS' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Inspect' |
| Pack | Pack value. Stored as 'PCK'. <br /> _Database Value:_ 'PCK' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Pack' |
| Unpack | Unpack value. Stored as 'UPK'. <br /> _Database Value:_ 'UPK' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Unpack' |
| Kit | Kit value. Stored as 'KIT'. <br /> _Database Value:_ 'KIT' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Kit' |
| Dekit | Dekit value. Stored as 'DKT'. <br /> _Database Value:_ 'DKT' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'Dekit' |
| Count | Count value. Stored as 'CNT'. <br /> _Database Value:_ 'CNT' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'Count' |
| UserTask | UserTask value. Stored as 'TSK'. <br /> _Database Value:_ 'TSK' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'UserTask' |
| ComponentDispatch | ComponentDispatch value. Stored as 'CDP'. <br /> _Database Value:_ 'CDP' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'ComponentDispatch' |
| ComponentReceive | ComponentReceive value. Stored as 'CRC'. <br /> _Database Value:_ 'CRC' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'ComponentReceive' |
| Assemble | Assemble value. Stored as 'ASM'. <br /> _Database Value:_ 'ASM' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'Assemble' |
| Disassemble | Disassemble value. Stored as 'DSM'. <br /> _Database Value:_ 'DSM' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'Disassemble' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.WarehouseOrder.TaskType`

_Front-End Recalc Expressions:_  
`obj.WarehouseOrder.TaskType`

## Reference Details

### Document

The owner document. The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LogisticUnit

Logistic unit, which should be used in the operation. `Filter(multi eq)` `Introduced in version 21.1.1.18`

_Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Lot

The lot of the product, which should be used. null for operations, which are not lot-specific, or when any lot can be used. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.26`

_Type_: **[WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The product, which should be used for the operation. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

The product variant, which should be used. `Filter(multi eq)` `Introduced in version 21.1.1.18`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity. null for operations, which are not quantity-related. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### SerialNumber

The serial number of the product, which should be used. null for operations, which are not serial number-specific, or when any serial number can be used. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ToWarehouseLocation

Destination warehouse location. null for operations, which do not specify destination location. `Filter(multi eq)`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WarehouseLocation

Location, where the opeartion should be performed. null for operations, which do not require location. `Filter(multi eq)`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WarehouseOrder

The <see cref="WarehouseOrder"/> to which this WarehouseOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### WarehouseWorker

Human or robot worker, which should execute the operation. null means that the line is shared among all workers, assigned to the order. `Filter(multi eq)`

_Type_: **[WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.WarehouseOrder.WarehouseWorker`

_Front-End Recalc Expressions:_  
`obj.WarehouseOrder.WarehouseWorker`
### WarehouseZone

The warehouse zone, in which the operation should be performed. null for operations which do not require specific zone. `Filter(multi eq)`

_Type_: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.WarehouseLocation != null), obj.WarehouseLocation.WarehouseZone, obj.WarehouseZone)`

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

