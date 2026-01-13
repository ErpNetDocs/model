---
uid: Logistics.Wms.Warehouses
---
# Logistics.Wms.Warehouses Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Physical warehouse. Entity: Wms_Warehouses (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
  * [Logistics.Wms.WarehouseLocations](Logistics.Wms.WarehouseLocations.md)  
  * [Logistics.Wms.WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md)  
  * [Logistics.Wms.WarehouseZones](Logistics.Wms.WarehouseZones.md)  
  * [Logistics.Wms.WarehousePolicies](Logistics.Wms.WarehousePolicies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Logistics.Wms.Warehouses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Wms.Warehouses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Wms.Warehouses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Logistics.Wms.Warehouses.md#id) | guid |  
| [Name](Logistics.Wms.Warehouses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the warehouse (multilanguage). `Required` `Filter(eq;like)` 
| [Notes](Logistics.Wms.Warehouses.md#notes) | string (max) __nullable__ | Notes for this Warehouse. 
| [ObjectVersion](Logistics.Wms.Warehouses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Locations | [WarehouseLocations](Logistics.Wms.WarehouseLocations.md) | List of `WarehouseLocation`(Logistics.Wms.WarehouseLocations.md) child objects, based on the `Logistics.Wms.WarehouseLocation.Warehouse`(Logistics.Wms.WarehouseLocations.md#warehouse) back reference 
| Policies | [WarehousePolicies](Logistics.Wms.WarehousePolicies.md) | List of `WarehousePolicy`(Logistics.Wms.WarehousePolicies.md) child objects, based on the `Logistics.Wms.WarehousePolicy.Warehouse`(Logistics.Wms.WarehousePolicies.md#warehouse) back reference 
| Workers | [WarehouseWorkers](Logistics.Wms.WarehouseWorkers.md) | List of `WarehouseWorker`(Logistics.Wms.WarehouseWorkers.md) child objects, based on the `Logistics.Wms.WarehouseWorker.Warehouse`(Logistics.Wms.WarehouseWorkers.md#warehouse) back reference 
| Zones | [WarehouseZones](Logistics.Wms.WarehouseZones.md) | List of `WarehouseZone`(Logistics.Wms.WarehouseZones.md) child objects, based on the `Logistics.Wms.WarehouseZone.Warehouse`(Logistics.Wms.WarehouseZones.md#warehouse) back reference 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### Name

Name of the warehouse (multilanguage). `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Warehouse.

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

[!list limit=1000 erp.entity=Logistics.Wms.Warehouses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.Warehouses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_Warehouses

Domain API Entity Type: 
Logistics_Wms_Warehouse

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_Warehouses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_Warehouses?$top=10>

