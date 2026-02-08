---
uid: Logistics.Wms.WarehouseTransactions
---
# Logistics.Wms.WarehouseTransactions


Represents increase or decrease in the quantity available in a warehouse location.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseTransactions  
Base Table: Wms_Warehouse_Transactions  
Introduced In Version: 21.1.1.26  
API access:  ReadWrite  

## Visualization
Display Format: {TaskType} {CreationTimeUtc:yyyy-MM-dd HH:mm:ss.fff}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CatchQuantity](Logistics.Wms.WarehouseTransactions.md#catchquantity) | decimal (12, 3) __nullable__ | Catch (measured) quantity for the transaction. Positive values indicate transactions. Negative values are used for adjustments. NULL when catch measurement is not configured for the product.`Filter(eq;ge;le)` 
| [CreationTimeUtc](Logistics.Wms.WarehouseTransactions.md#creationtimeutc) | datetime | The creation time in UTC.`Required` `Default(NowUtc)` `Filter(eq;ge;le)` 
| [Direction](Logistics.Wms.WarehouseTransactions.md#direction) | [Direction](Logistics.Wms.WarehouseTransactions.md#direction) | Direction of the transaction - I=IN, O=OUT.`Required` `Default(&quot;I&quot;)` `Filter(eq)` 
| [IsAutoAccepted](Logistics.Wms.WarehouseTransactions.md#isautoaccepted) | boolean | Auto-flag indicating that the product was accepted as correct without being physically counted.`Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 26.1.3.87` 
| [Quantity](Logistics.Wms.WarehouseTransactions.md#quantity) | decimal (12, 3) | The transacted net change in quantity. Positive values indicate transactions. Negative values are used for adjustments.`Required` `Default(0)` `Filter(multi eq;ge;le)` 
| [QuantityBase](Logistics.Wms.WarehouseTransactions.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9` 
| [StandardQuantity](Logistics.Wms.WarehouseTransactions.md#standardquantity) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity according to the current measurement dimensions of the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9` 
| [TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype) | [TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype) | The type of the task (operation), which was transacted.`Required` `Filter(multi eq)` `Introduced in version 22.1.6.15` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CatchQuantityUnit](Logistics.Wms.WarehouseTransactions.md#catchquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of the catch quantity. NULL when catch measurement is not configured for the product. |
| [CreationUser](Logistics.Wms.WarehouseTransactions.md#creationuser) | [Users](Systems.Security.Users.md) | The creation user. |
| [LogisticUnit](Logistics.Wms.WarehouseTransactions.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | Logistic unit, which was transacted. NULL when the transaction was not for a logistic unit. |
| [Lot](Logistics.Wms.WarehouseTransactions.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot which was transacted. NULL when the transaction was not for a specific lot. |
| [Product](Logistics.Wms.WarehouseTransactions.md#product) | [Products](General.Products.Products.md) | The product, which was transacted. |
| [ProductVariant](Logistics.Wms.WarehouseTransactions.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was transacted. NULL when the transaction was not for a product variant. |
| [QuantityUnit](Logistics.Wms.WarehouseTransactions.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of quantity. |
| [SerialNumber](Logistics.Wms.WarehouseTransactions.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number which was transacted. NULL when the transaction was not for a specific serial number. |
| [Warehouse](Logistics.Wms.WarehouseTransactions.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse in which the transaction occurred. |
| [WarehouseLocation](Logistics.Wms.WarehouseTransactions.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location, where the transaction occurred. |
| [WarehouseOrder](Logistics.Wms.WarehouseTransactions.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) (nullable) | The order which created this transaction. NULL when this transaction was not based on order. |
| [WarehouseOrderLine](Logistics.Wms.WarehouseTransactions.md#warehouseorderline) | [WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable) | The order line which created this transaction. NULL when this transaction was not based on order line. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseTransactions.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseTransactions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Wms.WarehouseTransactions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.WarehouseTransactions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Wms.WarehouseTransactions.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Wms.WarehouseTransactions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CatchQuantity

Catch (measured) quantity for the transaction. Positive values indicate transactions. Negative values are used for adjustments. NULL when catch measurement is not configured for the product.`Filter(eq;ge;le)`

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The creation time in UTC.`Required` `Default(NowUtc)` `Filter(eq;ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Direction

Direction of the transaction - I=IN, O=OUT.`Required` `Default(&quot;I&quot;)` `Filter(eq)`

Type: **[Direction](Logistics.Wms.WarehouseTransactions.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Logistics.Wms.WarehouseTransactions.md#direction) data attribute  
Allowed Values (Logistics.Wms.WarehouseTransactionsRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| IN | IN value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'IN' |
| OUT | OUT value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 1 <br /> Domain API Value: 'OUT' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **IN**  
Show in UI: **ShownByDefault**  

### IsAutoAccepted

Auto-flag indicating that the product was accepted as correct without being physically counted.`Required` `Default(false)` `Filter(eq)` `ReadOnly` `Introduced in version 26.1.3.87`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Quantity

The transacted net change in quantity. Positive values indicate transactions. Negative values are used for adjustments.`Required` `Default(0)` `Filter(multi eq;ge;le)`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardQuantity

The theoretical quantity according to the current measurement dimensions of the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Introduced in version 22.1.5.9`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaskType

The type of the task (operation), which was transacted.`Required` `Filter(multi eq)` `Introduced in version 22.1.6.15`

Type: **[TaskType](Logistics.Wms.WarehouseTransactions.md#tasktype)**  
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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### CatchQuantityUnit

The measurement unit of the catch quantity. NULL when catch measurement is not configured for the product.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CreationUser

The creation user.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LogisticUnit

Logistic unit, which was transacted. NULL when the transaction was not for a logistic unit.

Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The lot which was transacted. NULL when the transaction was not for a specific lot.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, which was transacted.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

The product variant, which was transacted. NULL when the transaction was not for a product variant.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

The serial number which was transacted. NULL when the transaction was not for a specific serial number.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

The warehouse in which the transaction occurred.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseLocation

The warehouse location, where the transaction occurred.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseOrder

The order which created this transaction. NULL when this transaction was not based on order.

Type: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseOrderLine

The order line which created this transaction. NULL when this transaction was not based on order line.

Type: **[WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable)**  
Indexed: **True**  
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

