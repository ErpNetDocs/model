---
uid: Logistics.Wms.WarehouseReconciliationDetails
---
# Logistics.Wms.WarehouseReconciliationDetails


Contains detailed warehouse reconciliation data per location and product, including snapshot and counted quantities for comparison of expected and actual stock.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseReconciliationDetails  
Base Table: Wms_Warehouse_Reconciliation_Details  
Introduced In Version: 26.2.1.1  
API access:  ReadWrite  

## Visualization
Display Format: {WarehouseReconciliation.EntityName}  
Search Members: WarehouseReconciliation.EntityName  
Name Member: WarehouseReconciliation.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)  
Aggregate Root:  
[Logistics.Wms.WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CountedQuantityBase](Logistics.Wms.WarehouseReconciliationDetails.md#countedquantitybase) | decimal (12, 3) __nullable__ | The physically counted quantity recorded during the counting process in the base measurement unit. The value is filled after a user action (e.g. merging results) and can be edited before completing the reconciliation.`Filter(eq;ge;le)` 
| [LastAggregatedAt](Logistics.Wms.WarehouseReconciliationDetails.md#lastaggregatedat) | datetime __nullable__ | The date and time when the counted quantities were last aggregated into this line.`Filter(eq;ge;le)` `ReadOnly` 
| [ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) | [ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) | Indicates the current review state of the reconciliation detail line and how it should be processed in the inventory workflow.`Required` `Default(&quot;CRT&quot;)` `Filter(multi eq)` 
| [Session](Logistics.Wms.WarehouseReconciliationDetails.md#session) | int32 | The counting session in which this result was recorded.`Required` `Filter(eq)` `ReadOnly` 
| [SnapshotDateTime](Logistics.Wms.WarehouseReconciliationDetails.md#snapshotdatetime) | datetime | The date and time when the availability snapshot for this line was created.`Required` `Filter(eq;ge;le)` `ReadOnly` 
| [SnapshotQuantityBase](Logistics.Wms.WarehouseReconciliationDetails.md#snapshotquantitybase) | decimal (12, 3) | The expected quantity of the product at the time the availability snapshot is created, in the base measurement unit.`Required` `Filter(eq;ge;le)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseUnit](Logistics.Wms.WarehouseReconciliationDetails.md#baseunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The product’s base measurement unit. |
| [LogisticUnit](Logistics.Wms.WarehouseReconciliationDetails.md#logisticunit) | [LogisticUnits](Logistics.Common.LogisticUnits.md) (nullable) | The logistic unit in which the product is stored on this location. Empty when the quantity is not associated with a logistic unit. |
| [Lot](Logistics.Wms.WarehouseReconciliationDetails.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Batch/lot of the product, when applicable. |
| [Product](Logistics.Wms.WarehouseReconciliationDetails.md#product) | [Products](General.Products.Products.md) (nullable) | The product stored at the specified warehouse location. |
| [SerialNumber](Logistics.Wms.WarehouseReconciliationDetails.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product, when serialized tracking is enabled. |
| [Variant](Logistics.Wms.WarehouseReconciliationDetails.md#variant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | Product variant (e.g. size, color, configuration), when tracked. |
| [WarehouseLocation](Logistics.Wms.WarehouseReconciliationDetails.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | The warehouse location included in the reconciliation. |
| [WarehouseReconciliation](Logistics.Wms.WarehouseReconciliationDetails.md#warehousereconciliation) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | The source document to which this detail refers. |
| [WarehouseZone](Logistics.Wms.WarehouseReconciliationDetails.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) | The warehouse zone to which the location belongs. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseReconciliationDetails.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseReconciliationDetails.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehouseReconciliationDetails.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CountedQuantityBase

The physically counted quantity recorded during the counting process in the base measurement unit. The value is filled after a user action (e.g. merging results) and can be edited before completing the reconciliation.`Filter(eq;ge;le)`

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LastAggregatedAt

The date and time when the counted quantities were last aggregated into this line.`Filter(eq;ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReviewStatus

Indicates the current review state of the reconciliation detail line and how it should be processed in the inventory workflow.`Required` `Default(&quot;CRT&quot;)` `Filter(multi eq)`

Type: **[ReviewStatus](Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus)**  
Category: **System**  
Allowed values for the `ReviewStatus`(Logistics.Wms.WarehouseReconciliationDetails.md#reviewstatus) data attribute  
Allowed Values (Logistics.Wms.WarehouseReconciliationDetailsRepository.ReviewStatus Enum Members)  

| Value | Description |
| ---- | --- |
| Created | The line is created from the snapshot and has no warehouse orders yet. This status is set automatically by the system on creation and can exist only once. It cannot be assigned manually by a user.. Stored as 'CRT'. <br /> Database Value: 'CRT' <br /> Model Value: 0 <br /> Domain API Value: 'Created' |
| Started | Warehouse orders have been generated for this line. This status is set automatically by the system and cannot be assigned by a user.. Stored as 'STR'. <br /> Database Value: 'STR' <br /> Model Value: 1 <br /> Domain API Value: 'Started' |
| Finished | Counting for this line is completed and results are available for review. This status is set automatically by the system.. Stored as 'FIN'. <br /> Database Value: 'FIN' <br /> Model Value: 2 <br /> Domain API Value: 'Finished' |
| Approved | The result for this line has been reviewed and approved. The line is considered final and will be used when generating warehouse transactions.. Stored as 'APR'. <br /> Database Value: 'APR' <br /> Model Value: 3 <br /> Domain API Value: 'Approved' |
| Recount | The line requires additional counting and should be included when generating new warehouse orders.. Stored as 'RCN'. <br /> Database Value: 'RCN' <br /> Model Value: 4 <br /> Domain API Value: 'Recount' |
| Cancelled | The line is excluded from the reconciliation process and will not be counted or processed further.. Stored as 'CNL'. <br /> Database Value: 'CNL' <br /> Model Value: 5 <br /> Domain API Value: 'Cancelled' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Created**  
Show in UI: **ShownByDefault**  

### Session

The counting session in which this result was recorded.`Required` `Filter(eq)` `ReadOnly`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SnapshotDateTime

The date and time when the availability snapshot for this line was created.`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SnapshotQuantityBase

The expected quantity of the product at the time the availability snapshot is created, in the base measurement unit.`Required` `Filter(eq;ge;le)` `ReadOnly`

Type: **decimal (12, 3)**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### BaseUnit

The product’s base measurement unit.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LogisticUnit

The logistic unit in which the product is stored on this location. Empty when the quantity is not associated with a logistic unit.

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

The product stored at the specified warehouse location.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Serial number of the product, when serialized tracking is enabled.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Variant

Product variant (e.g. size, color, configuration), when tracked.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseLocation

The warehouse location included in the reconciliation.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseReconciliation

The source document to which this detail refers.

Type: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WarehouseZone

The warehouse zone to which the location belongs.

Type: **[WarehouseZones](Logistics.Wms.WarehouseZones.md)**  
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

