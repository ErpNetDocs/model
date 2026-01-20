---
uid: Logistics.Wms.WarehouseReconciliationLines
---
# Logistics.Wms.WarehouseReconciliationLines Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Warehouse reconciliation detail records. Each record specifies a warehouse location to be reconciled. Entity: Wms_Warehouse_Reconciliation_Lines (Introduced in version 26.1.3.87)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {WarehouseReconciliation.DocumentNo} {WarehouseReconciliation.DocumentType.TypeName:T}_  
Default Search Members:  
_WarehouseReconciliation.DocumentNo_  
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
| [DisplayText](Logistics.Wms.WarehouseReconciliationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Wms.WarehouseReconciliationLines.md#id) | guid |  
| [LineNo](Logistics.Wms.WarehouseReconciliationLines.md#lineno) | int32 | Consecutive number of the line in the document. `Required` `Filter(eq)` `ORD` 
| [ObjectVersion](Logistics.Wms.WarehouseReconciliationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Wms.WarehouseReconciliationLines.md#document) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | The owner document. Reconciliation document this line belongs to. `Required` `Filter(multi eq)` |
| [WarehouseLocation](Logistics.Wms.WarehouseReconciliationLines.md#warehouselocation) | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | Warehouse location to be counted. `Required` `Filter(multi eq)` |
| [WarehouseReconciliation](Logistics.Wms.WarehouseReconciliationLines.md#warehousereconciliation) | [WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md) | Reconciliation document this line belongs to. `Required` `Filter(multi eq)` `Owner` |
| [WarehouseWorker](Logistics.Wms.WarehouseReconciliationLines.md#warehouseworker) | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable) | Worker (human or robot) assigned to perform the counting. `Filter(multi eq)` |
| [WarehouseZone](Logistics.Wms.WarehouseReconciliationLines.md#warehousezone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders. `Filter(multi eq)` `Introduced in version 26.2.1.16` |


## Attribute Details

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

### LineNo

Consecutive number of the line in the document. `Required` `Filter(eq)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.WarehouseReconciliation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WarehouseReconciliation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. Reconciliation document this line belongs to. `Required` `Filter(multi eq)`

_Type_: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseLocation

Warehouse location to be counted. `Required` `Filter(multi eq)`

_Type_: **[WarehouseLocations](Logistics.Wms.WarehouseLocations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseReconciliation

Reconciliation document this line belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WarehouseReconciliations](Logistics.Wms.WarehouseReconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### WarehouseWorker

Worker (human or robot) assigned to perform the counting. `Filter(multi eq)`

_Type_: **[WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WarehouseZone

Zone used to determine which locations are included when taking availability/snapshot, and later to split the generated Warehouse Orders. The zone is maintained separately from the location and is used only for scope and splitting of orders. `Filter(multi eq)` `Introduced in version 26.2.1.16`

_Type_: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
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

