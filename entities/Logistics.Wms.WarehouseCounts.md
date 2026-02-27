---
uid: Logistics.Wms.WarehouseCounts
---
# Logistics.Wms.WarehouseCounts


Captures raw physical count entries recorded in the warehouse operations before they are processed or consolidated by the system.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseCounts  
Base Table: Wms_Warehouse_Counts  
Introduced In Version: 26.2.1.4  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {QuantityValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseCounts](Logistics.Wms.WarehouseCounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUTC](Logistics.Wms.WarehouseCounts.md#creationtimeutc) | datetime | The timestamp when the counting entry was recorded (UTC).`Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Quantity](Logistics.Wms.WarehouseCounts.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity entered during the counting process, in the entered measurement unit.`Unit: QuantityUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [QuantityBase](Logistics.Wms.WarehouseCounts.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The converted quantity in the product’s base measurement unit.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Session](Logistics.Wms.WarehouseCounts.md#session) | int32 | The counting session number to which this entry belongs.`Required` `Filter(eq;ge;le)` `ReadOnly` 
| [StandardQuantityBase](Logistics.Wms.WarehouseCounts.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in the base measurement unit, calculated according to the product’s standard measurement ratio.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Void](Logistics.Wms.WarehouseCounts.md#void) | boolean | Indicates that the count record has been voided and should no longer be considered in the aggregation of counted quantities. Used when a counting entry was made by mistake or needs to be excluded from the reconciliation.`Required` `Default(false)` `Filter(eq)` `Introduced in version 26.2.1.65` 
| [VoidReason](Logistics.Wms.WarehouseCounts.md#voidreason) | string (254) __nullable__ | Specifies the reason for voiding the count record. Used to document why the counting entry is excluded from the reconciliation.`Introduced in version 26.2.1.65` 
| [VoidTime](Logistics.Wms.WarehouseCounts.md#voidtime) | datetime __nullable__ | The date and time when the count record was voided. Filled automatically by the system.`Filter(eq;ge;le)` `ReadOnly` `Introduced in version 26.2.1.65` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Wms.WarehouseCounts.md#creationuser) | [Users](Systems.Security.Users.md) | The user who recorded the counting entry. |
| [LogisticUnit](Logistics.Wms.WarehouseCounts.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | The logistic unit involved in the counting, when applicable. |
| [Lot](Logistics.Wms.WarehouseCounts.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Batch/lot of the product, when applicable. |
| [Product](Logistics.Wms.WarehouseCounts.md#product) | [Products](General.Products.Products.md) | The product that was counted. |
| [QuantityUnit](Logistics.Wms.WarehouseCounts.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit used when entering the quantity. |
| [SerialNumber](Logistics.Wms.WarehouseCounts.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number, when serialized tracking is enabled. |
| [SourceDocument](Logistics.Wms.WarehouseCounts.md#sourcedocument) | [Documents](General.Documents.Documents.md) (nullable) | Requisition, reconciliation, or other document which initiated the counting. |
| [Variant](Logistics.Wms.WarehouseCounts.md#variant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | Product variant (e.g. size, color, configuration), when tracked. |
| [VoidUser](Logistics.Wms.WarehouseCounts.md#voiduser) | [Users](Systems.Security.Users.md) (nullable) | The user who voided the count record. Filled automatically by the system. |
| [WarehouseLocation](Logistics.Wms.WarehouseCounts.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location where the counting occurred. |
| [WarehouseOrder](Logistics.Wms.WarehouseCounts.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | Warehouse order which initiated the counting. |
| [WarehouseOrderLine](Logistics.Wms.WarehouseCounts.md#warehouseorderline) | [WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable) | Indicates for which Warehouse Order line this count entry was recorded. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseCounts.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseCounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Wms.WarehouseCounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.WarehouseCounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Wms.WarehouseCounts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Wms.WarehouseCounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTimeUTC

The timestamp when the counting entry was recorded (UTC).`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity entered during the counting process, in the entered measurement unit.`Unit: QuantityUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

The converted quantity in the product’s base measurement unit.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Session

The counting session number to which this entry belongs.`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardQuantityBase

The theoretical quantity in the base measurement unit, calculated according to the product’s standard measurement ratio.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Void

Indicates that the count record has been voided and should no longer be considered in the aggregation of counted quantities. Used when a counting entry was made by mistake or needs to be excluded from the reconciliation.`Required` `Default(false)` `Filter(eq)` `Introduced in version 26.2.1.65`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### VoidReason

Specifies the reason for voiding the count record. Used to document why the counting entry is excluded from the reconciliation.`Introduced in version 26.2.1.65`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### VoidTime

The date and time when the count record was voided. Filled automatically by the system.`Filter(eq;ge;le)` `ReadOnly` `Introduced in version 26.2.1.65`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### CreationUser

The user who recorded the counting entry.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LogisticUnit

The logistic unit involved in the counting, when applicable.

Type: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

Batch/lot of the product, when applicable.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product that was counted.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit used when entering the quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Serial number, when serialized tracking is enabled.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SourceDocument

Requisition, reconciliation, or other document which initiated the counting.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Variant

Product variant (e.g. size, color, configuration), when tracked.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VoidUser

The user who voided the count record. Filled automatically by the system.

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseLocation

The warehouse location where the counting occurred.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseOrder

Warehouse order which initiated the counting.

Type: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseOrderLine

Indicates for which Warehouse Order line this count entry was recorded.

Type: **[WarehouseOrderLines](Logistics.Wms.WarehouseOrderLines.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseCounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseCounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseCounts

Domain API Entity Type: 
Logistics_Wms_WarehouseCount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseCounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseCounts?$top=10>

