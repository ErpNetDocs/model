---
uid: Logistics.Wms.WarehouseTransactions
---
# Logistics.Wms.WarehouseTransactions Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Represents increase or decrease in the quantity available in a warehouse location. Entity: Wms_Warehouse_Transactions (Introduced in version 21.1.1.26)

## Default Visualization
Default Display Text Format:  
_{TaskType} {CreationTimeUtc:yyyy-MM-dd HH:mm:ss.fff}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CatchQuantity](Logistics.Wms.WarehouseTransactions.md#catchquantity) | decimal (12, 3) __nullable__ | Catch (measured) quantity for the transaction. Positive values indicate transactions. Negative values are used for adjustments. null when catch measurement is not configured for the product. `Filter(eq;ge;le)` 
| [CreationTimeUtc](Logistics.Wms.WarehouseTransactions.md#creationtimeutc) | datetime | The creation time in UTC. `Required` `Default(NowUtc)` `Filter(eq;ge;le)` 
| [Direction](Logistics.Wms.WarehouseTransactions.md#direction) | [Direction](Logistics.Wms.WarehouseTransactions.md#direction) | Direction of the transaction - I=IN, O=OUT. `Required` `Default("I")` `Filter(eq)` 
| [DisplayText](Logistics.Wms.WarehouseTransactions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Wms.WarehouseTransactions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.WarehouseTransactions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Logistics.Wms.WarehouseTransactions.md#id) | guid |  
| [IsAutoAccepted](Logistics.Wms.WarehouseTransactions.md#isautoaccepted) | boolean | Auto-flag indicating that the product was accepted as correct without being physically counted. `Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 26.1.3.87` 
| [ObjectVersion](Logistics.Wms.WarehouseTransactions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Wms.WarehouseTransactions.md#quantity) | decimal (12, 3) | The transacted net change in quantity. Positive values indicate transactions. Negative values are used for adjustments. `Required` `Default(0)` `Filter(multi eq;ge;le)` 
| [QuantityBase](Logistics.Wms.WarehouseTransactions.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9` 
| [StandardQuantity](Logistics.Wms.WarehouseTransactions.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity according to the current measurement dimensions of the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9` 
| [TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype) | [TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype) | The type of the task (operation), which was transacted. `Required` `Filter(multi eq)` `Introduced in version 22.1.6.15` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CatchQuantityUnit](Logistics.Wms.WarehouseTransactions.md#catchquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of the catch quantity. null when catch measurement is not configured for the product. `Filter(multi eq)` |
| [CreationUser](Logistics.Wms.WarehouseTransactions.md#creationuser) | [Users](Systems.Security.Users.md) | The creation user. `Required` `Filter(multi eq)` |
| [LogisticUnit](Logistics.Wms.WarehouseTransactions.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | Logistic unit, which was transacted. null when the transaction was not for a logistic unit. `Filter(multi eq)` |
| [Lot](Logistics.Wms.WarehouseTransactions.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot which was transacted. null when the transaction was not for a specific lot. `Filter(multi eq)` |
| [Product](Logistics.Wms.WarehouseTransactions.md#product) | [Products](General.Products.Products.md) | The product, which was transacted. `Required` `Filter(multi eq)` |
| [ProductVariant](Logistics.Wms.WarehouseTransactions.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was transacted. null when the transaction was not for a product variant. `Filter(multi eq)` |
| [QuantityUnit](Logistics.Wms.WarehouseTransactions.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of quantity. `Required` `Filter(multi eq)` |
| [SerialNumber](Logistics.Wms.WarehouseTransactions.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number which was transacted. null when the transaction was not for a specific serial number. `Filter(multi eq)` |
| [Warehouse](Logistics.Wms.WarehouseTransactions.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse in which the transaction occurred. `Required` `Filter(multi eq)` |
| [WarehouseLocation](Logistics.Wms.WarehouseTransactions.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location, where the transaction occurred. `Required` `Filter(multi eq)` |
| [WarehouseOrder](Logistics.Wms.WarehouseTransactions.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) (nullable) | The order which created this transaction. null when this transaction was not based on order. `Filter(multi eq)` |
| [WarehouseOrderLine](Logistics.Wms.WarehouseTransactions.md#warehouseorderline) | [WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable) | The order line which created this transaction. null when this transaction was not based on order line. `Filter(multi eq)` |


## Attribute Details

### CatchQuantity

Catch (measured) quantity for the transaction. Positive values indicate transactions. Negative values are used for adjustments. null when catch measurement is not configured for the product. `Filter(eq;ge;le)`

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CreationTimeUtc

The creation time in UTC. `Required` `Default(NowUtc)` `Filter(eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### Direction

Direction of the transaction - I=IN, O=OUT. `Required` `Default("I")` `Filter(eq)`

_Type_: **[Direction](Logistics.Wms.WarehouseTransactions.md#direction)**  
_Category_: **System**  
Allowed values for the `Direction`(Logistics.Wms.WarehouseTransactions.md#direction) data attribute  
_Allowed Values (Logistics.Wms.WarehouseTransactionsRepository.Direction Enum Members)_  

| Value | Description |
| ---- | --- |
| IN | IN value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'IN' |
| OUT | OUT value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'OUT' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **IN**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### IsAutoAccepted

Auto-flag indicating that the product was accepted as correct without being physically counted. `Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 26.1.3.87`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The transacted net change in quantity. Positive values indicate transactions. Negative values are used for adjustments. `Required` `Default(0)` `Filter(multi eq;ge;le)`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardQuantity

The theoretical quantity according to the current measurement dimensions of the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TaskType

The type of the task (operation), which was transacted. `Required` `Filter(multi eq)` `Introduced in version 22.1.6.15`

_Type_: **[TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype)**  
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
_Show in UI_: **ShownByDefault**  


## Reference Details

### CatchQuantityUnit

The measurement unit of the catch quantity. null when catch measurement is not configured for the product. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CreationUser

The creation user. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LogisticUnit

Logistic unit, which was transacted. null when the transaction was not for a logistic unit. `Filter(multi eq)`

_Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The lot which was transacted. null when the transaction was not for a specific lot. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, which was transacted. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

The product variant, which was transacted. null when the transaction was not for a product variant. `Filter(multi eq)`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

The serial number which was transacted. null when the transaction was not for a specific serial number. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Warehouse

The warehouse in which the transaction occurred. `Required` `Filter(multi eq)`

_Type_: **[Warehouses](Logistics.Wms.Warehouses.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseLocation

The warehouse location, where the transaction occurred. `Required` `Filter(multi eq)`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseOrder

The order which created this transaction. null when this transaction was not based on order. `Filter(multi eq)`

_Type_: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseOrderLine

The order line which created this transaction. null when this transaction was not based on order line. `Filter(multi eq)`

_Type_: **[WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseTransactions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseTransactions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseTransactions

Domain API Entity Type: 
Logistics_Wms_WarehouseTransaction

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseTransactions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseTransactions?$top=10>

