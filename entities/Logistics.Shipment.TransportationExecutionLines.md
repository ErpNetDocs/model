---
uid: Logistics.Shipment.TransportationExecutionLines
---
# Logistics.Shipment.TransportationExecutionLines Entity

**Namespace:** [Logistics.Shipment](Logistics.Shipment.md)  

Contains details of executions of transportation order lines. Entity: Log_Transportation_Execution_Lines (Introduced in version 18.2)
## Renamed
**New name:** [Logistics.Transportation.TransportationExecutionLines](Logistics.Transportation.TransportationExecutionLines.md)  



## Default Visualization
Default Display Text Format:  
_{LineNo}. {TransportationExecution.DocumentNo} {TransportationExecution.DocumentType.TypeName:T}_  
Default Search Members:  
_TransportationExecution.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)  
Aggregate Root:  
[Logistics.Shipment.TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Logistics.Shipment.TransportationExecutionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExecutionDate](Logistics.Shipment.TransportationExecutionLines.md#executiondate) | date | The date when the operation was executed. `Required` `Filter(ge;le)` 
| [ExecutionTime](Logistics.Shipment.TransportationExecutionLines.md#executiontime) | time | The time when the operation was executed. `Required` `Filter(ge;le)` 
| [Id](Logistics.Shipment.TransportationExecutionLines.md#id) | guid |  
| [LineNo](Logistics.Shipment.TransportationExecutionLines.md#lineno) | int32 | Consecutive line number within this execution. `Required` 
| [Notes](Logistics.Shipment.TransportationExecutionLines.md#notes) | string (max) __nullable__ | Notes for this Transportation<br />ExecutionLine. 
| [ObjectVersion](Logistics.Shipment.TransportationExecutionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype) | [OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype) | The type of operation being executed. L=Loading; U=Unloading; O=Other. `Required` 
| [PalletNumber](Logistics.Shipment.TransportationExecutionLines.md#palletnumber) | string (32) __nullable__ | Pallet number, when applicable. null when unknown or not applicable. 
| [PalletsCount](Logistics.Shipment.TransportationExecutionLines.md#palletscount) | int32 __nullable__ | Number of pallets affected by this operation. null when unknown or N/A. 
| [VolumeCbm](Logistics.Shipment.TransportationExecutionLines.md#volumecbm) | int32 __nullable__ | Cargo volume in cubic meters, affected by this operation. null when unknown or N/A. 
| [WeightKg](Logistics.Shipment.TransportationExecutionLines.md#weightkg) | int32 __nullable__ | Cargo weight in kg, affected by this operation. null when unknown or N/A. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Shipment.TransportationExecutionLines.md#document) | [TransportationExecutions](Logistics.Shipment.TransportationExecutions.md) | The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` |
| [ExecutionOfTransportation<br />OrderLine](Logistics.Shipment.TransportationExecutionLines.md#executionoftransportationorderline) | [TransportationOrderLines](Logistics.Shipment.TransportationOrderLines.md) | The transportation order line, which is executed. `Required` `Filter(multi eq)` |
| [GeoPoint](Logistics.Shipment.TransportationExecutionLines.md#geopoint) | [GeoPoints](General.Geography.GeoPoints.md) | The geographic point, where the operation is executed. `Required` `Filter(multi eq)` |
| [TransportationExecution](Logistics.Shipment.TransportationExecutionLines.md#transportationexecution) | [TransportationExecutions](Logistics.Shipment.TransportationExecutions.md) | The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExecutionDate

The date when the operation was executed. `Required` `Filter(ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.TransportationExecution.ExecutionDate`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.ExecutionDate`
### ExecutionTime

The time when the operation was executed. `Required` `Filter(ge;le)`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.TransportationExecution.ExecutionTime`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.ExecutionTime`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive line number within this execution. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this TransportationExecutionLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OperationType

The type of operation being executed. L=Loading; U=Unloading; O=Other. `Required`

_Type_: **[OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype)**  
_Category_: **System**  
Allowed values for the `OperationType`(Logistics.Shipment.TransportationExecutionLines.md#operationtype) data attribute  
_Allowed Values (Logistics.Shipment.TransportationExecutionLinesRepository.OperationType Enum Members)_  

| Value | Description |
| ---- | --- |
| Loading | Loading value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Loading' |
| Unloading | Unloading value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Unloading' |
| Other | Other value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### PalletNumber

Pallet number, when applicable. null when unknown or not applicable.

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### PalletsCount

Number of pallets affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VolumeCbm

Cargo volume in cubic meters, affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### WeightKg

Cargo weight in kg, affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)`

_Type_: **[TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExecutionOfTransportationOrderLine

The transportation order line, which is executed. `Required` `Filter(multi eq)`

_Type_: **[TransportationOrderLines](Logistics.Shipment.TransportationOrderLines.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### GeoPoint

The geographic point, where the operation is executed. `Required` `Filter(multi eq)`

_Type_: **[GeoPoints](General.Geography.GeoPoints.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.TransportationExecution.GeoPoint`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.GeoPoint`
### TransportationExecution

The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationExecutionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationExecutionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Shipment_TransportationExecutionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_TransportationExecutionLines?$top=10>

