---
uid: Applications.Fleet.Vehicles
---
# Applications.Fleet.Vehicles


Contains vehicle definitions

## General
Namespace: [Applications.Fleet](Applications.Fleet.md)  
Repository: Applications.Fleet.Vehicles  
Base Table: Fleet_Vehicles  
API access:  ReadWrite  

## Visualization
Display Format: {VehicleRegistrationNumber}  
Search Members: VehicleRegistrationNumber  
Code Member: VehicleRegistrationNumber  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  
  * [Applications.Fleet.VehicleEquipment](Applications.Fleet.VehicleEquipment.md)  
  * [Logistics.Transportation.TransportationVehicles](Logistics.Transportation.TransportationVehicles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActiveFrom](Applications.Fleet.Vehicles.md#activefrom) | datetime __nullable__ | The date and time, when the vehicle has been purchased or started to be managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2` 
| [ActiveTill](Applications.Fleet.Vehicles.md#activetill) | datetime __nullable__ | The date and time, when the vehicle has been sold or has stopped being managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2` 
| [AuthorityMaximum<br />LadenMassKg](Applications.Fleet.Vehicles.md#authoritymaximumladenmasskg) | int32 __nullable__ | Maximum permissible laden mass, as determined by the registration authority. 
| [CrewCount](Applications.Fleet.Vehicles.md#crewcount) | int32 __nullable__ | Crew members count. For road vehicles = 1; for trailers, coaches and wagons =0; air and water vehicles may have higher counts. `Default(1)` `Filter(eq;ge;le)` 
| [EngineIdentificationNumber](Applications.Fleet.Vehicles.md#engineidentificationnumber) | string (20) __nullable__ | Engine identification number. `Filter(eq;like)` 
| [EnginePowerhp](Applications.Fleet.Vehicles.md#enginepowerhp) | int32 __nullable__ | Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)` 
| [EngineSizecc](Applications.Fleet.Vehicles.md#enginesizecc) | int32 __nullable__ | Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)` 
| [FuelCapacity](Applications.Fleet.Vehicles.md#fuelcapacity) | int32 __nullable__ | Maximum fuel capacity of the engine or the battery in the fuel measurement unit. 
| [FuelCompsumption](Applications.Fleet.Vehicles.md#fuelcompsumption) | decimal (7, 1) __nullable__ | Average fuel consumption in the fuel measurement unit for 1 operational unit. 
| [FuelType](Applications.Fleet.Vehicles.md#fueltype) | string (64) __nullable__ | Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)` 
| [IsActive](Applications.Fleet.Vehicles.md#isactive) | boolean | True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Filter(eq)` `Introduced in version 18.2` 
| [IssuingAuthority](Applications.Fleet.Vehicles.md#issuingauthority) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)` 
| [Make](Applications.Fleet.Vehicles.md#make) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)` 
| [ManufactureYear](Applications.Fleet.Vehicles.md#manufactureyear) | int32 __nullable__ | The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)` 
| [MaximumSpeedKmH](Applications.Fleet.Vehicles.md#maximumspeedkmh) | int32 __nullable__ | Maximum speed in km/h. 
| [Model](Applications.Fleet.Vehicles.md#model) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The model of the vehicle. `Filter(eq;like)` 
| [Notes](Applications.Fleet.Vehicles.md#notes) | string (max) __nullable__ | Notes for this Vehicle. 
| [PrimaryColor](Applications.Fleet.Vehicles.md#primarycolor) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The primary color of the vehicle. null means that the value is unknown or not applicable. `Filter(eq;like)` 
| [SeatingPlacesCount](Applications.Fleet.Vehicles.md#seatingplacescount) | int32 __nullable__ | Number of seating places, excluding driver. `Filter(eq;ge;le)` 
| [StandingPlacesCount](Applications.Fleet.Vehicles.md#standingplacescount) | int32 __nullable__ | Number of standing places, if applicable. 
| [TechnicalMaximum<br />LadenMassKg](Applications.Fleet.Vehicles.md#technicalmaximumladenmasskg) | int32 __nullable__ | Maximum technically permissible laden mass in kg. 
| [TrainsetMaximumLadenMassKg](Applications.Fleet.Vehicles.md#trainsetmaximumladenmasskg) | int32 __nullable__ | Maximum permissible laden mass of a whole trainset, including the vehicle. 
| [VehicleIdentification<br />Number](Applications.Fleet.Vehicles.md#vehicleidentificationnumber) | string (20) __nullable__ | VIN, aka Chassis number. `Filter(eq;like)` 
| [VehicleMassKg](Applications.Fleet.Vehicles.md#vehiclemasskg) | int32 __nullable__ | Vehicle own mass in kg. 
| [VehicleRegistrationNumber](Applications.Fleet.Vehicles.md#vehicleregistrationnumber) | string (16) | The registration plate number. Can be numeric or alphanumeric code. It should be unique within the Issuing_Authority. `Required` `Filter(eq;like)` 
| [VehicleType](Applications.Fleet.Vehicles.md#vehicletype) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | Type of vehicle - e.g. automobile, bus, etc. null means the value is unknown. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.Fleet.Vehicles.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company that manages thе Vehicle. `Filter(multi eq)` `Introduced in version 24.1.4.79` |
| [FuelMeasurementUnit](Applications.Fleet.Vehicles.md#fuelmeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit in which the fuel is measured. E.g. liters for automobiles, Watt-hours for electrics, etc. null means unknown. `Filter(multi eq)` |
| [MaintenanceProfile](Applications.Fleet.Vehicles.md#maintenanceprofile) | [MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) (nullable) | When not null, specifies, that the vehicle should be maintained according to the specified profile. Assigning a profile creates plan assignments for the vehicle. Ultimately, the specific plan assignments are taken into consideration, when planning vehicle maintenance. The profile is only for conveniently assigning multiple plans. `Filter(multi eq)` |
| [ManagedAsset](Applications.Fleet.Vehicles.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable) | Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74` |
| [OperationalMeasurementUnit](Applications.Fleet.Vehicles.md#operationalmeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit in which the operation of the vehicle is measured. E.g. km for automobiles, hrs for airplanes, etc. null means that the unit is unknown. `Filter(multi eq)` |
| [OwnerParty](Applications.Fleet.Vehicles.md#ownerparty) | [Parties](General.Contacts.Parties.md) (nullable) | Vehicle owner. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.Vehicles.md#id) | guid |  
| [ObjectVersion](Applications.Fleet.Vehicles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Fleet.Vehicles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Fleet.Vehicles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Fleet.Vehicles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Fleet.Vehicles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Equipment | [VehicleEquipment](Applications.Fleet.VehicleEquipment.md) | List of `VehicleEquipment`(Applications.Fleet.VehicleEquipment.md) child objects, based on the `Applications.Fleet.VehicleEquipment.Vehicle`(Applications.Fleet.VehicleEquipment.md#vehicle) back reference 
| TransportationVehicles | [TransportationVehicles](Logistics.Transportation.TransportationVehicles.md) | List of `TransportationVehicle`(Logistics.Transportation.TransportationVehicles.md) child objects, based on the `Logistics.Transportation.TransportationVehicle.Vehicle`(Logistics.Transportation.TransportationVehicles.md#vehicle) back reference 


## Attribute Details

### ActiveFrom

The date and time, when the vehicle has been purchased or started to be managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ActiveTill

The date and time, when the vehicle has been sold or has stopped being managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AuthorityMaximumLadenMassKg

Maximum permissible laden mass, as determined by the registration authority.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CrewCount

Crew members count. For road vehicles = 1; for trailers, coaches and wagons =0; air and water vehicles may have higher counts. `Default(1)` `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### EngineIdentificationNumber

Engine identification number. `Filter(eq;like)`

Type: **string (20) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### EnginePowerhp

Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EngineSizecc

Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FuelCapacity

Maximum fuel capacity of the engine or the battery in the fuel measurement unit.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FuelCompsumption

Average fuel consumption in the fuel measurement unit for 1 operational unit.

Type: **decimal (7, 1) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FuelType

Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### IsActive

True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Filter(eq)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IssuingAuthority

The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Make

The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ManufactureYear

The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MaximumSpeedKmH

Maximum speed in km/h.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Model

The model of the vehicle. `Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Vehicle.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PrimaryColor

The primary color of the vehicle. null means that the value is unknown or not applicable. `Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SeatingPlacesCount

Number of seating places, excluding driver. `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandingPlacesCount

Number of standing places, if applicable.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TechnicalMaximumLadenMassKg

Maximum technically permissible laden mass in kg.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TrainsetMaximumLadenMassKg

Maximum permissible laden mass of a whole trainset, including the vehicle.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VehicleIdentificationNumber

VIN, aka Chassis number. `Filter(eq;like)`

Type: **string (20) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### VehicleMassKg

Vehicle own mass in kg.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### VehicleRegistrationNumber

The registration plate number. Can be numeric or alphanumeric code. It should be unique within the Issuing_Authority. `Required` `Filter(eq;like)`

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### VehicleType

Type of vehicle - e.g. automobile, bus, etc. null means the value is unknown. `Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### EnterpriseCompany

The Enterprise Company that manages thе Vehicle. `Filter(multi eq)` `Introduced in version 24.1.4.79`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### FuelMeasurementUnit

The measurement unit in which the fuel is measured. E.g. liters for automobiles, Watt-hours for electrics, etc. null means unknown. `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MaintenanceProfile

When not null, specifies, that the vehicle should be maintained according to the specified profile. Assigning a profile creates plan assignments for the vehicle. Ultimately, the specific plan assignments are taken into consideration, when planning vehicle maintenance. The profile is only for conveniently assigning multiple plans. `Filter(multi eq)`

Type: **[MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74`

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OperationalMeasurementUnit

The measurement unit in which the operation of the vehicle is measured. E.g. km for automobiles, hrs for airplanes, etc. null means that the unit is unknown. `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OwnerParty

Vehicle owner. `Filter(multi eq)`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Applications.Fleet.Vehicles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.Vehicles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Fleet_Vehicles

Domain API Entity Type: 
Applications_Fleet_Vehicle

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Fleet_Vehicles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Fleet_Vehicles?$top=10>

