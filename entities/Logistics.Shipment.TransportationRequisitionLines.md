---
uid: Logistics.Shipment.TransportationRequisitionLines
---
# Logistics.Shipment.TransportationRequisitionLines Entity

**Namespace:** [Logistics.Shipment](Logistics.Shipment.md)  

One line in a client requisition for transportation. Different lines usually represent requisitions for different cargo types. Entity: Log_Transportation_Requisition_Lines
## Renamed
**New name:** [Logistics.Transportation.TransportationRequisitionLines](Logistics.Transportation.TransportationRequisitionLines.md)  



## Default Visualization
Default Display Text Format:  
_{LineNo}. {TransportationRequisition.DocumentNo} {TransportationRequisition.DocumentType.TypeName:T}_  
Default Search Members:  
_TransportationRequisition.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md)  
Aggregate Root:  
[Logistics.Shipment.TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContentsDescription](Logistics.Shipment.TransportationRequisitionLines.md#contentsdescription) | string (128) | Textual description of the cargo contents. `Required` 
| [DisplayText](Logistics.Shipment.TransportationRequisitionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Shipment.TransportationRequisitionLines.md#id) | guid |  
| [LineNo](Logistics.Shipment.TransportationRequisitionLines.md#lineno) | int32 | Line number, unique within the TransportationRequisition. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationRequisition (in order to allow insertions with adjustment documents). `Required` `Filter(eq)` 
| [ObjectVersion](Logistics.Shipment.TransportationRequisitionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PalletsCount](Logistics.Shipment.TransportationRequisitionLines.md#palletscount) | int32 __nullable__ | Number of palettes comprising the cargo. null when it is unknown. 
| [ParentLineNo](Logistics.Shipment.TransportationRequisitionLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(eq)` 
| [VolumeCbm](Logistics.Shipment.TransportationRequisitionLines.md#volumecbm) | int32 __nullable__ | The volume of the cargo, in CBM (cubic meters). null when it is unknown. 
| [WeightKg](Logistics.Shipment.TransportationRequisitionLines.md#weightkg) | int32 __nullable__ | The weight of the cargo, in KG (kilogramms). null when it is unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Shipment.TransportationRequisitionLines.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) | The type of the transported cargo. `Required` `Filter(multi eq)` |
| [Document](Logistics.Shipment.TransportationRequisitionLines.md#document) | [TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md) | The <see cref="Transportation<br />Requisition"/> to which this Transportation<br />RequisitionLine belongs. `Required` `Filter(multi eq)` |
| [ParentDocument](Logistics.Shipment.TransportationRequisitionLines.md#parentdocument) | [Documents](General.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [TransportationRequisition](Logistics.Shipment.TransportationRequisitionLines.md#transportationrequisition) | [TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md) | The <see cref="Transportation<br />Requisition"/> to which this Transportation<br />RequisitionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ContentsDescription

Textual description of the cargo contents. `Required`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Line number, unique within the TransportationRequisition. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationRequisition (in order to allow insertions with adjustment documents). `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.TransportationRequisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.TransportationRequisition.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PalletsCount

Number of palettes comprising the cargo. null when it is unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(eq)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VolumeCbm

The volume of the cargo, in CBM (cubic meters). null when it is unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### WeightKg

The weight of the cargo, in KG (kilogramms). null when it is unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CargoType

The type of the transported cargo. `Required` `Filter(multi eq)`

_Type_: **[CargoTypes](Logistics.Shipment.CargoTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Document

The <see cref="TransportationRequisition"/> to which this TransportationRequisitionLine belongs. `Required` `Filter(multi eq)`

_Type_: **[TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TransportationRequisition

The <see cref="TransportationRequisition"/> to which this TransportationRequisitionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TransportationRequisitions](Logistics.Shipment.TransportationRequisitions.md)**  
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

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationRequisitionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationRequisitionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Shipment_TransportationRequisitionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_TransportationRequisitionLines?$top=10>

