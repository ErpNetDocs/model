---
uid: Logistics.Wms.WarehouseZones
---
# Logistics.Wms.WarehouseZones


One zone within a warehouse. Each zone can have different rack structure and different temperature and other properties.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseZones  
Base Table: Wms_Warehouse_Zones  
Introduced In Version: 22.1.4.67  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
Aggregate Root:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Logistics.Wms.WarehouseZones.md#code) | string (32) | Zone code, unique within the warehouse.`Required` `Filter(multi eq;like)` |
| [Name](Logistics.Wms.WarehouseZones.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multi-language name of the zone.`Required` `Filter(eq;like)` |
| [Notes](Logistics.Wms.WarehouseZones.md#notes) | string (max) __nullable__ | Notes for this WarehouseZone. |
| [ZoneType](Logistics.Wms.WarehouseZones.md#zonetype) | [ZoneType](Logistics.Wms.WarehouseZones.md#zonetype) __nullable__ | Specifies the primary functional purpose of the Warehouse Zone. The zone type can be used by warehouse processes to determine appropriate source, destination, or processing zones when planning and executing warehouse operations. RCZ=Receiving; BLK=Bulk; PKZ=Picking; LBZ=Labeling; PAZ=Packing; ASZ=Assembly; DSZ=Disassembly; SHZ=Shipping; QRZ=Quarantine; GNZ=General; UZA=User Defined 1; UZB=User Defined 2; UZC=User Defined 3; UZD=User Defined 4.`Filter(multi eq)` `Introduced in version 27.1.0.99` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Parent](Logistics.Wms.WarehouseZones.md#parent) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | The parent Warehouse Zone of the current Warehouse Zone. `Filter(multi eq)` |
| [Warehouse](Logistics.Wms.WarehouseZones.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse in which the zone is located. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehouseZones.md#id) | guid |  |
| [ObjectVersion](Logistics.Wms.WarehouseZones.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [DisplayText](Logistics.Wms.WarehouseZones.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Code

Zone code, unique within the warehouse.`Required` `Filter(multi eq;like)`

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.GetNextCode( obj.Parent)`

Front-End Recalc Expressions:  
`obj.GetNextCode( obj.Parent)`
### Name

Multi-language name of the zone.`Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WarehouseZone.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ZoneType

Specifies the primary functional purpose of the Warehouse Zone. The zone type can be used by warehouse processes to determine appropriate source, destination, or processing zones when planning and executing warehouse operations. RCZ=Receiving; BLK=Bulk; PKZ=Picking; LBZ=Labeling; PAZ=Packing; ASZ=Assembly; DSZ=Disassembly; SHZ=Shipping; QRZ=Quarantine; GNZ=General; UZA=User Defined 1; UZB=User Defined 2; UZC=User Defined 3; UZD=User Defined 4.`Filter(multi eq)` `Introduced in version 27.1.0.99`

Type: **[ZoneType](Logistics.Wms.WarehouseZones.md#zonetype) __nullable__**  
Category: **System**  
Allowed values for the `ZoneType`(Logistics.Wms.WarehouseZones.md#zonetype) data attribute  
Allowed Values (Logistics.Wms.WarehouseZonesRepository.ZoneType Enum Members)  

| Value | Description |
| ---- | --- |
| Receiving | A zone where incoming goods are unloaded, received, and initially processed.. Stored as 'RCZ'. <br /> Database Value: 'RCZ' <br /> Model Value: 0 <br /> Domain API Value: 'Receiving' |
| Bulk | A primary storage zone for goods and logistic units, including reserve quantities and full pallets.. Stored as 'BLK'. <br /> Database Value: 'BLK' <br /> Model Value: 1 <br /> Domain API Value: 'Bulk' |
| Picking | A zone from which products are collected for the execution of Pick tasks.. Stored as 'PKZ'. <br /> Database Value: 'PKZ' <br /> Model Value: 2 <br /> Domain API Value: 'Picking' |
| Labeling | A zone where required localized or market-specific labels are applied to products.. Stored as 'LBZ'. <br /> Database Value: 'LBZ' <br /> Model Value: 3 <br /> Domain API Value: 'Labeling' |
| Packing | A zone where products or components are packed, repacked, or consolidated into packages or logistic units.. Stored as 'PAZ'. <br /> Database Value: 'PAZ' <br /> Model Value: 4 <br /> Domain API Value: 'Packing' |
| Assembly | A zone where components are physically assembled into finished or semi-finished products.. Stored as 'ASZ'. <br /> Database Value: 'ASZ' <br /> Model Value: 5 <br /> Domain API Value: 'Assembly' |
| Disassembly | A zone where products are disassembled into their individual components.. Stored as 'DSZ'. <br /> Database Value: 'DSZ' <br /> Model Value: 6 <br /> Domain API Value: 'Disassembly' |
| Shipping | A zone where completed goods are prepared for loading and departure from the warehouse.. Stored as 'SHZ'. <br /> Database Value: 'SHZ' <br /> Model Value: 7 <br /> Domain API Value: 'Shipping' |
| Quarantine | A zone where goods are temporarily isolated and excluded from standard warehouse processes.. Stored as 'QRZ'. <br /> Database Value: 'QRZ' <br /> Model Value: 8 <br /> Domain API Value: 'Quarantine' |
| General | A zone without a single specific primary purpose.. Stored as 'GNZ'. <br /> Database Value: 'GNZ' <br /> Model Value: 9 <br /> Domain API Value: 'General' |
| UserDefined1 | A user-defined zone type that can be used according to the specific warehouse processes.. Stored as 'UZA'. <br /> Database Value: 'UZA' <br /> Model Value: 10 <br /> Domain API Value: 'UserDefined1' |
| UserDefined2 | A user-defined zone type that can be used according to the specific warehouse processes.. Stored as 'UZB'. <br /> Database Value: 'UZB' <br /> Model Value: 11 <br /> Domain API Value: 'UserDefined2' |
| UserDefined3 | A user-defined zone type that can be used according to the specific warehouse processes.. Stored as 'UZC'. <br /> Database Value: 'UZC' <br /> Model Value: 12 <br /> Domain API Value: 'UserDefined3' |
| UserDefined4 | A user-defined zone type that can be used according to the specific warehouse processes.. Stored as 'UZD'. <br /> Database Value: 'UZD' <br /> Model Value: 13 <br /> Domain API Value: 'UserDefined4' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### Parent

The parent Warehouse Zone of the current Warehouse Zone. `Filter(multi eq)`

Type: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

The warehouse in which the zone is located.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseZones erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseZones erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseZones

Domain API Entity Type: 
Logistics_Wms_WarehouseZone

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseZones?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseZones?$top=10>

