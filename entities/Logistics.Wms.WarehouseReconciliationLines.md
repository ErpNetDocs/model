---
uid: Logistics.Wms.WarehouseReconciliationLines
---
# Logistics.Wms.WarehouseReconciliationLines


Warehouse reconciliation detail records. Each record specifies a warehouse location to be reconciled.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseReconciliationLines  
Base Table: Wms_Warehouse_Reconciliation_Lines  
Introduced In Version: 26.1.3.87  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {WarehouseReconciliation.DocumentNo} {WarehouseReconciliation.DocumentType.TypeName:T}  
Search Members: WarehouseReconciliation.DocumentNo  
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
| [LineNo](Logistics.Wms.WarehouseReconciliationLines.md#lineno) | int32 | Consecutive number of the line in the document. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Wms.WarehouseReconciliationLines.md#document) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | The owner document. Reconciliation document this line belongs to. `Required` `Filter(multi eq)` |
| [WarehouseLocation](Logistics.Wms.WarehouseReconciliationLines.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | Warehouse location to be counted. |
| [WarehouseReconciliation](Logistics.Wms.WarehouseReconciliationLines.md#warehousereconciliation) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | Reconciliation document this line belongs to. |
| [WarehouseWorker](Logistics.Wms.WarehouseReconciliationLines.md#warehouseworker) | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable) | Worker (human or robot) assigned to perform the counting. |
| [WarehouseZone](Logistics.Wms.WarehouseReconciliationLines.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseReconciliationLines.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehouseReconciliationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehouseReconciliationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineNo

Consecutive number of the line in the document.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WarehouseReconciliation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.WarehouseReconciliation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
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

The owner document. Reconciliation document this line belongs to. `Required` `Filter(multi eq)`

Type: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseLocation

Warehouse location to be counted.

Type: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseReconciliation

Reconciliation document this line belongs to.

Type: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WarehouseWorker

Worker (human or robot) assigned to perform the counting.

Type: **[WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WarehouseZone

Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders.

Type: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseReconciliationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseReconciliationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseReconciliationLines

Domain API Entity Type: 
Logistics_Wms_WarehouseReconciliationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseReconciliationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseReconciliationLines?$top=10>

