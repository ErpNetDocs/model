---
uid: Logistics.Transportation.TransportationOrderLines
---
# Logistics.Transportation.TransportationOrderLines Entity

**Namespace:** [Logistics.Transportation](Logistics.Transportation.md)  

Different cargoes of a transportation order. Entity: Log_Transportation_Order_Lines

## Renames

Old name: **Logistics.Shipment.TransportationOrderLines**  
New name: **Logistics.Transportation.TransportationOrderLines**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{LineNo}. {TransportationOrder.DocumentNo} {TransportationOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_TransportationOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Transportation.TransportationOrders](Logistics.Transportation.TransportationOrders.md)  
Aggregate Root:  
[Logistics.Transportation.TransportationOrders](Logistics.Transportation.TransportationOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContentsDescription](Logistics.Transportation.TransportationOrderLines.md#contentsdescription) | string (128) | Textual description of the cargo contents. `Required` 
| [DisplayText](Logistics.Transportation.TransportationOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Transportation.TransportationOrderLines.md#id) | guid |  
| [LineNo](Logistics.Transportation.TransportationOrderLines.md#lineno) | int32 | Line number, unique within the TransportationOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationOrder (in order to allow insertions with adjustment documents). `Required` `Filter(eq)` 
| [Notes](Logistics.Transportation.TransportationOrderLines.md#notes) | string (max) __nullable__ | Notes for this TransportationOrderLine. `Introduced in version 18.2` 
| [ObjectVersion](Logistics.Transportation.TransportationOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PalletsCount](Logistics.Transportation.TransportationOrderLines.md#palletscount) | int32 __nullable__ | Number of palettes comprising the cargo. null when it is unknown. 
| [ParentLineNo](Logistics.Transportation.TransportationOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(eq)` 
| [VolumeCbm](Logistics.Transportation.TransportationOrderLines.md#volumecbm) | int32 __nullable__ | The volume of the cargo, in CBM (cubic meters). null when it is unknown. 
| [WeightKg](Logistics.Transportation.TransportationOrderLines.md#weightkg) | int32 __nullable__ | The weight of the cargo, in KG (kilogramms). null when it is unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Transportation.TransportationOrderLines.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) | The type of the transported cargo. `Required` `Filter(multi eq)` |
| [Document](Logistics.Transportation.TransportationOrderLines.md#document) | [TransportationOrders](Logistics.Transportation.TransportationOrders.md) | The owner document. The <see cref="Transportation<br />Order"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` |
| [ParentDocument](Logistics.Transportation.TransportationOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [TransportationOrder](Logistics.Transportation.TransportationOrderLines.md#transportationorder) | [TransportationOrders](Logistics.Transportation.TransportationOrders.md) | The <see cref="Transportation<br />Order"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |


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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Line number, unique within the TransportationOrder. Usually is increasing number like 10, 20, 30, ... when initially entering the TransportationOrder (in order to allow insertions with adjustment documents). `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.TransportationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.TransportationOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this TransportationOrderLine. `Introduced in version 18.2`

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

### PalletsCount

Number of palettes comprising the cargo. null when it is unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(eq)`

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

The owner document. The <see cref="TransportationOrder"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[TransportationOrders](Logistics.Transportation.TransportationOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TransportationOrder

The <see cref="TransportationOrder"/> to which this TransportationOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TransportationOrders](Logistics.Transportation.TransportationOrders.md)**  
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

