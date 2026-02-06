---
uid: Logistics.Transportation.TransportationExecutionLines
---
# Logistics.Transportation.TransportationExecutionLines


Contains details of executions of transportation order lines.

## General
Namespace: [Logistics.Transportation](Logistics.Transportation.md)  
Repository: Logistics.Transportation.TransportationExecutionLines  
Base Table: Log_Transportation_Execution_Lines  
Introduced In Version: 18.2  
API access:  ReadWrite  

## Renames

Old name: Logistics.Shipment.TransportationExecutionLines  
New name: Logistics.Transportation.TransportationExecutionLines  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {LineNo}. {TransportationExecution.DocumentNo} {TransportationExecution.DocumentType.TypeName:T}  
Search Members: TransportationExecution.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Transportation.TransportationExecutions](Logistics.Transportation.TransportationExecutions.md)  
Aggregate Root:  
[Logistics.Transportation.TransportationExecutions](Logistics.Transportation.TransportationExecutions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExecutionDate](Logistics.Transportation.TransportationExecutionLines.md#executiondate) | date | The date when the operation was executed.[Required] [Filter(ge;le)] 
| [ExecutionTime](Logistics.Transportation.TransportationExecutionLines.md#executiontime) | time | The time when the operation was executed.[Required] [Filter(ge;le)] 
| [LineNo](Logistics.Transportation.TransportationExecutionLines.md#lineno) | int32 | Consecutive line number within this execution.[Required] 
| [Notes](Logistics.Transportation.TransportationExecutionLines.md#notes) | string (max) __nullable__ | Notes for this Transportation<br />ExecutionLine. 
| [OperationType](Logistics.Transportation.TransportationExecutionLines.md#operationtype) | [OperationType](Logistics.Transportation.TransportationExecutionLines.md#operationtype) | The type of operation being executed. L=Loading; U=Unloading; O=Other.[Required] 
| [PalletNumber](Logistics.Transportation.TransportationExecutionLines.md#palletnumber) | string (32) __nullable__ | Pallet number, when applicable. NULL when unknown or not applicable. 
| [PalletsCount](Logistics.Transportation.TransportationExecutionLines.md#palletscount) | int32 __nullable__ | Number of pallets affected by this operation. NULL when unknown or N/A. 
| [VolumeCbm](Logistics.Transportation.TransportationExecutionLines.md#volumecbm) | int32 __nullable__ | Cargo volume in cubic meters, affected by this operation. NULL when unknown or N/A. 
| [WeightKg](Logistics.Transportation.TransportationExecutionLines.md#weightkg) | int32 __nullable__ | Cargo weight in kg, affected by this operation. NULL when unknown or N/A. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Transportation.TransportationExecutionLines.md#document) | [TransportationExecutions](Logistics.Transportation.TransportationExecutions.md) | The owner document. The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` |
| [ExecutionOfTransportation<br />OrderLine](Logistics.Transportation.TransportationExecutionLines.md#executionoftransportationorderline) | [TransportationOrderLines](Logistics.Transportation.TransportationOrderLines.md) | The transportation order line, which is executed. |
| [GeoPoint](Logistics.Transportation.TransportationExecutionLines.md#geopoint) | [GeoPoints](General.Geography.GeoPoints.md) | The geographic point, where the operation is executed. |
| [TransportationExecution](Logistics.Transportation.TransportationExecutionLines.md#transportationexecution) | [TransportationExecutions](Logistics.Transportation.TransportationExecutions.md) | The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Transportation.TransportationExecutionLines.md#id) | guid |  
| [ObjectVersion](Logistics.Transportation.TransportationExecutionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Transportation.TransportationExecutionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ExecutionDate

The date when the operation was executed.[Required] [Filter(ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.TransportationExecution.ExecutionDate`

Front-End Recalc Expressions:  
`obj.TransportationExecution.ExecutionDate`
### ExecutionTime

The time when the operation was executed.[Required] [Filter(ge;le)]

Type: **time**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.TransportationExecution.ExecutionTime`

Front-End Recalc Expressions:  
`obj.TransportationExecution.ExecutionTime`
### LineNo

Consecutive line number within this execution.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this TransportationExecutionLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### OperationType

The type of operation being executed. L=Loading; U=Unloading; O=Other.[Required]

Type: **[OperationType](Logistics.Transportation.TransportationExecutionLines.md#operationtype)**  
Category: **System**  
Allowed values for the `OperationType`(Logistics.Transportation.TransportationExecutionLines.md#operationtype) data attribute  
Allowed Values (Logistics.Transportation.TransportationExecutionLinesRepository.OperationType Enum Members)  

| Value | Description |
| ---- | --- |
| Loading | Loading value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 0 <br /> Domain API Value: 'Loading' |
| Unloading | Unloading value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 1 <br /> Domain API Value: 'Unloading' |
| Other | Other value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 2 <br /> Domain API Value: 'Other' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PalletNumber

Pallet number, when applicable. NULL when unknown or not applicable.

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### PalletsCount

Number of pallets affected by this operation. NULL when unknown or N/A.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VolumeCbm

Cargo volume in cubic meters, affected by this operation. NULL when unknown or N/A.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WeightKg

Cargo weight in kg, affected by this operation. NULL when unknown or N/A.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### Document

The owner document. The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)`

Type: **[TransportationExecutions](Logistics.Transportation.TransportationExecutions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExecutionOfTransportationOrderLine

The transportation order line, which is executed.

Type: **[TransportationOrderLines](Logistics.Transportation.TransportationOrderLines.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### GeoPoint

The geographic point, where the operation is executed.

Type: **[GeoPoints](General.Geography.GeoPoints.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.TransportationExecution.GeoPoint`

Front-End Recalc Expressions:  
`obj.TransportationExecution.GeoPoint`
### TransportationExecution

The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[TransportationExecutions](Logistics.Transportation.TransportationExecutions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationExecutionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationExecutionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Transportation_TransportationExecutionLines

Domain API Entity Type: 
Logistics_Transportation_TransportationExecutionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Transportation_TransportationExecutionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Transportation_TransportationExecutionLines?$top=10>

