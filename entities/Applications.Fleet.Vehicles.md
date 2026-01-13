---
uid: Applications.Fleet.Vehicles
---
# Applications.Fleet.Vehicles Entity

**Namespace:** [Applications.Fleet](Applications.Fleet.md)  

Contains vehicle definitions. Entity: Fleet_Vehicles

## Default Visualization
Default Display Text Format:  
_{VehicleRegistrationNumber}_  
Default Search Members:  
_VehicleRegistrationNumber_  
Code Data Member:  
_VehicleRegistrationNumber_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Applications.Fleet.Vehicles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EngineIdentificationNumber](Applications.Fleet.Vehicles.md#engineidentificationnumber) | string (20) __nullable__ | Engine identification number. `Filter(eq;like)` 
| [EnginePowerhp](Applications.Fleet.Vehicles.md#enginepowerhp) | int32 __nullable__ | Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)` 
| [EngineSizecc](Applications.Fleet.Vehicles.md#enginesizecc) | int32 __nullable__ | Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)` 
| [ExternalId](Applications.Fleet.Vehicles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Fleet.Vehicles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FuelCapacity](Applications.Fleet.Vehicles.md#fuelcapacity) | int32 __nullable__ | Maximum fuel capacity of the engine or the battery in the fuel measurement unit. 
| [FuelCompsumption](Applications.Fleet.Vehicles.md#fuelcompsumption) | decimal (7, 1) __nullable__ | Average fuel consumption in the fuel measurement unit for 1 operational unit. 
| [FuelType](Applications.Fleet.Vehicles.md#fueltype) | string (64) __nullable__ | Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)` 
| [Id](Applications.Fleet.Vehicles.md#id) | guid |  
| [IsActive](Applications.Fleet.Vehicles.md#isactive) | boolean | True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Filter(eq)` `Introduced in version 18.2` 
| [IssuingAuthority](Applications.Fleet.Vehicles.md#issuingauthority) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)` 
| [Make](Applications.Fleet.Vehicles.md#make) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)` 
| [ManufactureYear](Applications.Fleet.Vehicles.md#manufactureyear) | int32 __nullable__ | The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)` 
| [MaximumSpeedKmH](Applications.Fleet.Vehicles.md#maximumspeedkmh) | int32 __nullable__ | Maximum speed in km/h. 
| [Model](Applications.Fleet.Vehicles.md#model) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | The model of the vehicle. `Filter(eq;like)` 
| [Notes](Applications.Fleet.Vehicles.md#notes) | string (max) __nullable__ | Notes for this Vehicle. 
| [ObjectVersion](Applications.Fleet.Vehicles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Equipment | [VehicleEquipment](Applications.Fleet.VehicleEquipment.md) | List of `VehicleEquipment`(Applications.Fleet.VehicleEquipment.md) child objects, based on the `Applications.Fleet.VehicleEquipment.Vehicle`(Applications.Fleet.VehicleEquipment.md#vehicle) back reference 
| TransportationVehicles | [TransportationVehicles](Logistics.Transportation.TransportationVehicles.md) | List of `TransportationVehicle`(Logistics.Transportation.TransportationVehicles.md) child objects, based on the `Logistics.Transportation.TransportationVehicle.Vehicle`(Logistics.Transportation.TransportationVehicles.md#vehicle) back reference 


## Attribute Details

### ActiveFrom

The date and time, when the vehicle has been purchased or started to be managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ActiveTill

The date and time, when the vehicle has been sold or has stopped being managed. Null when the date and time are unknown. `Filter(ge;le)` `Introduced in version 18.2`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### AuthorityMaximumLadenMassKg

Maximum permissible laden mass, as determined by the registration authority.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CrewCount

Crew members count. For road vehicles = 1; for trailers, coaches and wagons =0; air and water vehicles may have higher counts. `Default(1)` `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EngineIdentificationNumber

Engine identification number. `Filter(eq;like)`

_Type_: **string (20) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

### EnginePowerhp

Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### EngineSizecc

Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

### FuelCapacity

Maximum fuel capacity of the engine or the battery in the fuel measurement unit.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FuelCompsumption

Average fuel consumption in the fuel measurement unit for 1 operational unit.

_Type_: **decimal (7, 1) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### FuelType

Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Filter(eq)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IssuingAuthority

The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Make

The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ManufactureYear

The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MaximumSpeedKmH

Maximum speed in km/h.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Model

The model of the vehicle. `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Vehicle.

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

### PrimaryColor

The primary color of the vehicle. null means that the value is unknown or not applicable. `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SeatingPlacesCount

Number of seating places, excluding driver. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StandingPlacesCount

Number of standing places, if applicable.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TechnicalMaximumLadenMassKg

Maximum technically permissible laden mass in kg.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TrainsetMaximumLadenMassKg

Maximum permissible laden mass of a whole trainset, including the vehicle.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VehicleIdentificationNumber

VIN, aka Chassis number. `Filter(eq;like)`

_Type_: **string (20) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

### VehicleMassKg

Vehicle own mass in kg.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### VehicleRegistrationNumber

The registration plate number. Can be numeric or alphanumeric code. It should be unique within the Issuing_Authority. `Required` `Filter(eq;like)`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### VehicleType

Type of vehicle - e.g. automobile, bus, etc. null means the value is unknown. `Filter(eq;like)`

_Type_: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The Enterprise Company that manages thе Vehicle. `Filter(multi eq)` `Introduced in version 24.1.4.79`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### FuelMeasurementUnit

The measurement unit in which the fuel is measured. E.g. liters for automobiles, Watt-hours for electrics, etc. null means unknown. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MaintenanceProfile

When not null, specifies, that the vehicle should be maintained according to the specified profile. Assigning a profile creates plan assignments for the vehicle. Ultimately, the specific plan assignments are taken into consideration, when planning vehicle maintenance. The profile is only for conveniently assigning multiple plans. `Filter(multi eq)`

_Type_: **[MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74`

_Type_: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OperationalMeasurementUnit

The measurement unit in which the operation of the vehicle is measured. E.g. km for automobiles, hrs for airplanes, etc. null means that the unit is unknown. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OwnerParty

Vehicle owner. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

