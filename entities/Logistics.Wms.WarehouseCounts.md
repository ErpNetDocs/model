---
uid: Logistics.Wms.WarehouseCounts
---
# Logistics.Wms.WarehouseCounts Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Captures raw physical count entries recorded in the warehouse operations before they are processed or consolidated by the system. Entity: Wms_Warehouse_Counts (Introduced in version 26.2.1.4)

## Default Visualization
Default Display Text Format:  
_{Id}: {QuantityValue}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseCounts](Logistics.Wms.WarehouseCounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Logistics.Wms.WarehouseCounts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [CreationTimeUTC](Logistics.Wms.WarehouseCounts.md#creationtimeutc) | datetime | The timestamp when the counting entry was recorded (UTC). `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [DisplayText](Logistics.Wms.WarehouseCounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Wms.WarehouseCounts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.WarehouseCounts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Logistics.Wms.WarehouseCounts.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseCounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Wms.WarehouseCounts.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity entered during the counting process, in the entered measurement unit. `Unit: QuantityUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [QuantityBase](Logistics.Wms.WarehouseCounts.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The converted quantity in the product’s base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [Session](Logistics.Wms.WarehouseCounts.md#session) | int32 | The counting session number to which this entry belongs. `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [StandardQuantityBase](Logistics.Wms.WarehouseCounts.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in the base measurement unit, calculated according to the product’s standard measurement ratio. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Wms.WarehouseCounts.md#creationuser) | [Users](Systems.Security.Users.md) | The user who recorded the counting entry. `Required` `Filter(multi eq)` `ReadOnly` |
| [LogisticUnit](Logistics.Wms.WarehouseCounts.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | The logistic unit involved in the counting, when applicable. `Filter(multi eq)` `ReadOnly` |
| [Lot](Logistics.Wms.WarehouseCounts.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Batch/lot of the product, when applicable. `Filter(multi eq)` `ReadOnly` |
| [Product](Logistics.Wms.WarehouseCounts.md#product) | [Products](General.Products.Products.md) | The product that was counted. `Required` `Filter(multi eq)` `ReadOnly` |
| [QuantityUnit](Logistics.Wms.WarehouseCounts.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit used when entering the quantity. `Required` `Filter(multi eq)` `ReadOnly` |
| [SerialNumber](Logistics.Wms.WarehouseCounts.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number, when serialized tracking is enabled. `Filter(multi eq)` `ReadOnly` |
| [SourceDocument](Logistics.Wms.WarehouseCounts.md#sourcedocument) | [Documents](General.Documents.Documents.md) (nullable) | Requisition, reconciliation, or other document which initiated the counting. `Filter(multi eq)` `ReadOnly` |
| [Variant](Logistics.Wms.WarehouseCounts.md#variant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | Product variant (e.g. size, color, configuration), when tracked. `Filter(multi eq)` `ReadOnly` |
| [WarehouseLocation](Logistics.Wms.WarehouseCounts.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location where the counting occurred. `Required` `Filter(multi eq)` `ReadOnly` |
| [WarehouseOrder](Logistics.Wms.WarehouseCounts.md#warehouseorder) | [WarehouseOrders](Logistics.Wms.WarehouseOrders.md) | Warehouse order which initiated the counting. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CreationTimeUTC

The timestamp when the counting entry was recorded (UTC). `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity entered during the counting process, in the entered measurement unit. `Unit: QuantityUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The converted quantity in the product’s base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Session

The counting session number to which this entry belongs. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandardQuantityBase

The theoretical quantity in the base measurement unit, calculated according to the product’s standard measurement ratio. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreationUser

The user who recorded the counting entry. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LogisticUnit

The logistic unit involved in the counting, when applicable. `Filter(multi eq)` `ReadOnly`

_Type_: **[LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

Batch/lot of the product, when applicable. `Filter(multi eq)` `ReadOnly`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product that was counted. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit used when entering the quantity. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Serial number, when serialized tracking is enabled. `Filter(multi eq)` `ReadOnly`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SourceDocument

Requisition, reconciliation, or other document which initiated the counting. `Filter(multi eq)` `ReadOnly`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Variant

Product variant (e.g. size, color, configuration), when tracked. `Filter(multi eq)` `ReadOnly`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseLocation

The warehouse location where the counting occurred. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseOrder

Warehouse order which initiated the counting. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[WarehouseOrders](Logistics.Wms.WarehouseOrders.md)**  
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

