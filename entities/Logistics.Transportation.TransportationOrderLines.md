---
uid: Logistics.Transportation.TransportationOrderLines
---
# Logistics.Transportation.TransportationOrderLines


Different cargoes of a transportation order.

## General
Namespace: [Logistics.Transportation](Logistics.Transportation.md)  
Repository: Logistics.Transportation.TransportationOrderLines  
Base Table: Log_Transportation_Order_Lines  
API access:  ReadWrite  

## Renames

Old name: Logistics.Shipment.TransportationOrderLines  
New name: Logistics.Transportation.TransportationOrderLines  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {LineNo}. {TransportationOrder.DocumentNo} {TransportationOrder.DocumentType.TypeName:T}  
Search Members: TransportationOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Transportation.TransportationOrders](Logistics.Transportation.TransportationOrders.md)  
Aggregate Root:  
[Logistics.Transportation.TransportationOrders](Logistics.Transportation.TransportationOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContentsDescription](Logistics.Transportation.TransportationOrderLines.md#contentsdescription) | string (128) | Textual description of the cargo contents.[Required] 
| [LineNo](Logistics.Transportation.TransportationOrderLines.md#lineno) | int32 | Line number, unique within the TransportationOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationOrder (in order to allow insertions with adjustment documents). `Required` `Filter(eq)` 
| [Notes](Logistics.Transportation.TransportationOrderLines.md#notes) | string (max) __nullable__ | Notes for this TransportationOrderLine. `Introduced in version 18.2` 
| [PalletsCount](Logistics.Transportation.TransportationOrderLines.md#palletscount) | int32 __nullable__ | Number of palettes comprising the cargo. NULL when it is unknown. 
| [ParentLineNo](Logistics.Transportation.TransportationOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)] 
| [VolumeCbm](Logistics.Transportation.TransportationOrderLines.md#volumecbm) | int32 __nullable__ | The volume of the cargo, in CBM (cubic meters). NULL when it is unknown. 
| [WeightKg](Logistics.Transportation.TransportationOrderLines.md#weightkg) | int32 __nullable__ | The weight of the cargo, in KG (kilogramms). NULL when it is unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Transportation.TransportationOrderLines.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) | The type of the transported cargo. |
| [Document](Logistics.Transportation.TransportationOrderLines.md#document) | [TransportationOrders](Logistics.Transportation.TransportationOrders.md) | The owner document. The <see cref="Transportation<br />Order"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` |
| [ParentDocument](Logistics.Transportation.TransportationOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [TransportationOrder](Logistics.Transportation.TransportationOrderLines.md#transportationorder) | [TransportationOrders](Logistics.Transportation.TransportationOrders.md) | The <see cref="Transportation<br />Order"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Transportation.TransportationOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Transportation.TransportationOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Transportation.TransportationOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ContentsDescription

Textual description of the cargo contents.[Required]

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### LineNo

Line number, unique within the TransportationOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationOrder (in order to allow insertions with adjustment documents). `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.TransportationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.TransportationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this TransportationOrderLine. `Introduced in version 18.2`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PalletsCount

Number of palettes comprising the cargo. NULL when it is unknown.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VolumeCbm

The volume of the cargo, in CBM (cubic meters). NULL when it is unknown.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WeightKg

The weight of the cargo, in KG (kilogramms). NULL when it is unknown.

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

### CargoType

The type of the transported cargo.

Type: **[CargoTypes](Logistics.Shipment.CargoTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="TransportationOrder"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[TransportationOrders](Logistics.Transportation.TransportationOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TransportationOrder

The <see cref="TransportationOrder"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[TransportationOrders](Logistics.Transportation.TransportationOrders.md)**  
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

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Transportation_TransportationOrderLines

Domain API Entity Type: 
Logistics_Transportation_TransportationOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Transportation_TransportationOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Transportation_TransportationOrderLines?$top=10>

