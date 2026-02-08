---
uid: Logistics.Transportation.TransportationVehicles
---
# Logistics.Transportation.TransportationVehicles


A vehicle, which is used for transportation. One actual vehicle might be defined multiple times as transportation vehicle - for different modes of transportation or cargo types.

## General
Namespace: [Logistics.Transportation](Logistics.Transportation.md)  
Repository: Logistics.Transportation.TransportationVehicles  
Base Table: Log_Transportation_Vehicles  
API access:  ReadWrite  

## Renames

Old name: Logistics.Shipment.TransportationVehicles  
New name: Logistics.Transportation.TransportationVehicles  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Code}: {Vehicle.VehicleType:T}, {Vehicle.VehicleRegistrationNumber:T}  
Search Members: Code; Vehicle.VehicleRegistrationNumber  
Code Member: Code  
Name Member: Vehicle.VehicleRegistrationNumber  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  
Aggregate Root:  
[Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Logistics.Transportation.TransportationVehicles.md#code) | string (16) | The unique code (or call sign) of this transportation vehicle.`Required` `Filter(eq;like)` `ORD` 
| [MaxCargoWeightKg](Logistics.Transportation.TransportationVehicles.md#maxcargoweightkg) | int32 __nullable__ | The maximum weight of the cargo (in kg), which can be transported. NULL when this is unknown and no limit should be enforced. 
| [MaxPalletsCount](Logistics.Transportation.TransportationVehicles.md#maxpalletscount) | int32 __nullable__ | The maximum number of pallets, which can be transported by the vehicle. NULL when this is unknown and no limit should be enforced. 
| [Notes](Logistics.Transportation.TransportationVehicles.md#notes) | string (max) __nullable__ | Notes for this TransportationVehicle. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CargoType](Logistics.Transportation.TransportationVehicles.md#cargotype) | [CargoTypes](Logistics.Shipment.CargoTypes.md) | The cargo type supported by this transportation vehicle. |
| [Carrier](Logistics.Transportation.TransportationVehicles.md#carrier) | [Carriers](Logistics.Shipment.Carriers.md) (nullable) | The carrier, operating the vehicle. NULL for our own vehicles. |
| [EnterpriseCompany](Logistics.Transportation.TransportationVehicles.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company to which the transportation vehicle will be bound. |
| [TransportationMode](Logistics.Transportation.TransportationVehicles.md#transportationmode) | [TransportationModes](Logistics.Transportation.TransportationModes.md) | The mode of transportation provided by this transportation vehicle. The same base vehicle might be used for more than one mode. |
| [Vehicle](Logistics.Transportation.TransportationVehicles.md#vehicle) | [Vehicles](Applications.Fleet.Vehicles.md) | The definition of the base vehicle. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Transportation.TransportationVehicles.md#id) | guid |  
| [ObjectVersion](Logistics.Transportation.TransportationVehicles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Transportation.TransportationVehicles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The unique code (or call sign) of this transportation vehicle.`Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### MaxCargoWeightKg

The maximum weight of the cargo (in kg), which can be transported. NULL when this is unknown and no limit should be enforced.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MaxPalletsCount

The maximum number of pallets, which can be transported by the vehicle. NULL when this is unknown and no limit should be enforced.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this TransportationVehicle.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

The cargo type supported by this transportation vehicle.

Type: **[CargoTypes](Logistics.Shipment.CargoTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Carrier

The carrier, operating the vehicle. NULL for our own vehicles.

Type: **[Carriers](Logistics.Shipment.Carriers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company to which the transportation vehicle will be bound.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TransportationMode

The mode of transportation provided by this transportation vehicle. The same base vehicle might be used for more than one mode.

Type: **[TransportationModes](Logistics.Transportation.TransportationModes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Vehicle

The definition of the base vehicle.

Type: **[Vehicles](Applications.Fleet.Vehicles.md)**  
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

