---
uid: Logistics.Transportation.TransportationVehicles
---
# Logistics.Transportation.TransportationVehicles Entity

**Namespace:** [Logistics.Transportation](Logistics.Transportation.md)  

A vehicle, which is used for transportation. One actual vehicle might be defined multiple times as transportation vehicle - for different modes of transportation or cargo types. Entity: Log_Transportation_Vehicles

## Renames

Old name: **Logistics.Shipment.TransportationVehicles**  
New name: **Logistics.Transportation.TransportationVehicles**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{Code}: {Vehicle.VehicleType:T}, {Vehicle.VehicleRegistrationNumber:T}_  
Default Search Members:  
_Code; Vehicle.VehicleRegistrationNumber_  
Code Data Member:  
_Code_  
Name Data Member:  
_Vehicle.VehicleRegistrationNumber_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  
Aggregate Root:  
[Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Logistics.Transportation.TransportationVehicles.md#code) | string (16) | The unique code (or call sign) of this transportation vehicle. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Logistics.Transportation.TransportationVehicles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Transportation.TransportationVehicles.md#id) | guid |  
| [MaxCargoWeightKg](Logistics.Transportation.TransportationVehicles.md#maxcargoweightkg) | int32 __nullable__ | The maximum weight of the cargo (in kg), which can be transported. null when this is unknown and no limit should be enforced. 
| [MaxPalletsCount](Logistics.Transportation.TransportationVehicles.md#maxpalletscount) | int32 __nullable__ | The maximum number of pallets, which can be transported by the vehicle. null when this is unknown and no limit should be enforced. 
| [Notes](Logistics.Transportation.TransportationVehicles.md#notes) | string (max) __nullable__ | Notes for this TransportationVehicle. 
| [ObjectVersion](Logistics.Transportation.TransportationVehicles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Transportation.TransportationVehicles.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) | The cargo type supported by this transportation vehicle. `Required` `Filter(multi eq)` |
| [Carrier](Logistics.Transportation.TransportationVehicles.md#carrier) | [Carriers](Logistics.Shipment.Carriers.md) (nullable) | The carrier, operating the vehicle. null for our own vehicles. `Filter(multi eq)` `Introduced in version 23.1.2.9` |
| [EnterpriseCompany](Logistics.Transportation.TransportationVehicles.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company to which the transportation vehicle will be bound. `Required` `Filter(multi eq)` |
| [TransportationMode](Logistics.Transportation.TransportationVehicles.md#transportationmode) | [TransportationModes](Logistics.Transportation.TransportationModes.md) | The mode of transportation provided by this transportation vehicle. The same base vehicle might be used for more than one mode. `Required` `Filter(multi eq)` |
| [Vehicle](Logistics.Transportation.TransportationVehicles.md#vehicle) | [Vehicles](Applications.Fleet.Vehicles.md) | The definition of the base vehicle. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Code

The unique code (or call sign) of this transportation vehicle. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
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

### MaxCargoWeightKg

The maximum weight of the cargo (in kg), which can be transported. null when this is unknown and no limit should be enforced.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MaxPalletsCount

The maximum number of pallets, which can be transported by the vehicle. null when this is unknown and no limit should be enforced.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this TransportationVehicle.

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


## Reference Details

### CargoType

The cargo type supported by this transportation vehicle. `Required` `Filter(multi eq)`

_Type_: **[CargoTypes](Logistics.Shipment.CargoTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Carrier

The carrier, operating the vehicle. null for our own vehicles. `Filter(multi eq)` `Introduced in version 23.1.2.9`

_Type_: **[Carriers](Logistics.Shipment.Carriers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company to which the transportation vehicle will be bound. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TransportationMode

The mode of transportation provided by this transportation vehicle. The same base vehicle might be used for more than one mode. `Required` `Filter(multi eq)`

_Type_: **[TransportationModes](Logistics.Transportation.TransportationModes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Vehicle

The definition of the base vehicle. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Vehicles](Applications.Fleet.Vehicles.md)**  
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

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationVehicles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Transportation.TransportationVehicles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Transportation_TransportationVehicles

Domain API Entity Type: 
Logistics_Transportation_TransportationVehicle

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Transportation_TransportationVehicles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Transportation_TransportationVehicles?$top=10>

