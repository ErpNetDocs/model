---
uid: Logistics.Wms.WarehouseReconciliationDetails
---
# Logistics.Wms.WarehouseReconciliationDetails Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Contains detailed warehouse reconciliation data per location and product, including snapshot and counted quantities for comparison of expected and actual stock. Entity: Wms_Warehouse_Reconciliation_Details (Introduced in version 26.2.1.1)

## Default Visualization
Default Display Text Format:  
_{WarehouseReconciliation.EntityName}_  
Default Search Members:  
_WarehouseReconciliation.EntityName_  
Name Data Member:  
_WarehouseReconciliation.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)  
Aggregate Root:  
[Logistics.Wms.WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CountedQuantityBase](Logistics.Wms.WarehouseReconciliationDetails.md#countedquantitybase) | decimal (12, 3) __nullable__ | The physically counted quantity recorded during the counting process in the base measurement unit. The value is filled after a user action (e.g. merging results) and can be edited before completing the reconciliation. `Filter(eq;ge;le)` 
| [DisplayText](Logistics.Wms.WarehouseReconciliationDetails.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Wms.WarehouseReconciliationDetails.md#id) | guid |  
| [LastAggregatedAt](Logistics.Wms.WarehouseReconciliationDetails.md#lastaggregatedat) | datetime __nullable__ | The date and time when the counted quantities were last aggregated into this line. `Filter(eq;ge;le)` `ReadOnly` 
| [ObjectVersion](Logistics.Wms.WarehouseReconciliationDetails.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) | [ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) | Indicates the current review state of the reconciliation detail line and how it should be processed in the inventory workflow. `Required` `Default("CRT")` `Filter(multi eq)` 
| [Session](Logistics.Wms.WarehouseReconciliationDetails.md#session) | int32 | The counting session in which this result was recorded. `Required` `Filter(eq)` `ReadOnly` 
| [SnapshotDateTime](Logistics.Wms.WarehouseReconciliationDetails.md#snapshotdatetime) | datetime | The date and time when the availability snapshot for this line was created. `Required` `Filter(eq;ge;le)` `ReadOnly` 
| [SnapshotQuantityBase](Logistics.Wms.WarehouseReconciliationDetails.md#snapshotquantitybase) | decimal (12, 3) | The expected quantity of the product at the time the availability snapshot is created, in the base measurement unit. `Required` `Filter(eq;ge;le)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseUnit](Logistics.Wms.WarehouseReconciliationDetails.md#baseunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The product’s base measurement unit. `Filter(multi eq)` `ReadOnly` |
| [LogisticUnit](Logistics.Wms.WarehouseReconciliationDetails.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | The logistic unit in which the product is stored on this location. Empty when the quantity is not associated with a logistic unit. `Filter(multi eq)` `ReadOnly` |
| [Lot](Logistics.Wms.WarehouseReconciliationDetails.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Batch/lot of the product, when applicable. `Filter(multi eq)` `ReadOnly` |
| [Product](Logistics.Wms.WarehouseReconciliationDetails.md#product) | [Products](General.Products.Products.md) (nullable) | The product stored at the specified warehouse location. `Filter(multi eq)` `ReadOnly` |
| [SerialNumber](Logistics.Wms.WarehouseReconciliationDetails.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product, when serialized tracking is enabled. `Filter(multi eq)` `ReadOnly` |
| [Variant](Logistics.Wms.WarehouseReconciliationDetails.md#variant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | Product variant (e.g. size, color, configuration), when tracked. `Filter(multi eq)` `ReadOnly` |
| [WarehouseLocation](Logistics.Wms.WarehouseReconciliationDetails.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location included in the reconciliation. `Required` `Filter(multi eq)` `ReadOnly` |
| [WarehouseReconciliation](Logistics.Wms.WarehouseReconciliationDetails.md#warehousereconciliation) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | The source document to which this detail refers. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [WarehouseZone](Logistics.Wms.WarehouseReconciliationDetails.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) | The warehouse zone to which the location belongs. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### CountedQuantityBase

The physically counted quantity recorded during the counting process in the base measurement unit. The value is filled after a user action (e.g. merging results) and can be edited before completing the reconciliation. `Filter(eq;ge;le)`

_Type_: **decimal (12, 3) __nullable__**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LastAggregatedAt

The date and time when the counted quantities were last aggregated into this line. `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ReviewStatus

Indicates the current review state of the reconciliation detail line and how it should be processed in the inventory workflow. `Required` `Default("CRT")` `Filter(multi eq)`

_Type_: **[ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus)**  
_Category_: **System**  
Allowed values for the `ReviewStatus`(Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) data attribute  
_Allowed Values (Logistics.Wms.WarehouseReconciliationDetailsRepository.ReviewStatus Enum Members)_  

| Value | Description |
| ---- | --- |
| Created | The line is created from the snapshot and has no warehouse orders yet. This status is set automatically by the system on creation and can exist only once. It cannot be assigned manually by a user.. Stored as 'CRT'. <br /> _Database Value:_ 'CRT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Created' |
| Started | Warehouse orders have been generated for this line. This status is set automatically by the system and cannot be assigned by a user.. Stored as 'STR'. <br /> _Database Value:_ 'STR' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Started' |
| Finished | Counting for this line is completed and results are available for review. This status is set automatically by the system.. Stored as 'FIN'. <br /> _Database Value:_ 'FIN' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Finished' |
| Approved | The result for this line has been reviewed and approved. The line is considered final and will be used when generating warehouse transactions.. Stored as 'APR'. <br /> _Database Value:_ 'APR' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Approved' |
| Recount | The line requires additional counting and should be included when generating new warehouse orders.. Stored as 'RCN'. <br /> _Database Value:_ 'RCN' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Recount' |
| Cancelled | The line is excluded from the reconciliation process and will not be counted or processed further.. Stored as 'CNL'. <br /> _Database Value:_ 'CNL' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Cancelled' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Created**  
_Show in UI_: **ShownByDefault**  

### Session

The counting session in which this result was recorded. `Required` `Filter(eq)` `ReadOnly`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SnapshotDateTime

The date and time when the availability snapshot for this line was created. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SnapshotQuantityBase

The expected quantity of the product at the time the availability snapshot is created, in the base measurement unit. `Required` `Filter(eq;ge;le)` `ReadOnly`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BaseUnit

The product’s base measurement unit. `Filter(multi eq)` `ReadOnly`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LogisticUnit

The logistic unit in which the product is stored on this location. Empty when the quantity is not associated with a logistic unit. `Filter(multi eq)` `ReadOnly`

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

The product stored at the specified warehouse location. `Filter(multi eq)` `ReadOnly`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Serial number of the product, when serialized tracking is enabled. `Filter(multi eq)` `ReadOnly`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
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

The warehouse location included in the reconciliation. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseReconciliation

The source document to which this detail refers. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### WarehouseZone

The warehouse zone to which the location belongs. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[WarehouseZones](Logistics.Wms.WarehouseZones.md)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseReconciliationDetails erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseReconciliationDetails erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseReconciliationDetails

Domain API Entity Type: 
Logistics_Wms_WarehouseReconciliationDetail

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseReconciliationDetails?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseReconciliationDetails?$top=10>

