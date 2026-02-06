---
uid: Applications.Fleet.VehicleMaintenancePlanAssignments
---
# Applications.Fleet.VehicleMaintenancePlanAssignments


Represents assignment of a maintenance plan to a vehicle.

## General
Namespace: [Applications.Fleet](Applications.Fleet.md)  
Repository: Applications.Fleet.VehicleMaintenancePlanAssignments  
Base Table: Fleet_Vehicle_Maintenance_Plan_Assignments  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {VehicleId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Fleet.VehicleMaintenancePlanAssignments](Applications.Fleet.VehicleMaintenancePlanAssignments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Applications.Fleet.VehicleMaintenancePlanAssignments.md#isactive) | boolean | Specifies whether the plan is active.[Required] [Default(true)] [Filter(eq)] 
| [LastMaintenanceMileageKm](Applications.Fleet.VehicleMaintenancePlanAssignments.md#lastmaintenancemileagekm) | int32 __nullable__ | The mileage of the vehicle (in Kilometers), when the last maintenance of this type occurred. Should be specified for plans, which require mileage check. 
| [LastMaintenanceTripCount](Applications.Fleet.VehicleMaintenancePlanAssignments.md#lastmaintenancetripcount) | int32 __nullable__ | The trip count of the vehicle, when the last maintenance of this type occurred. Should be specified for plans, which trip count check. 
| [Notes](Applications.Fleet.VehicleMaintenancePlanAssignments.md#notes) | string (max) __nullable__ | Notes for this VehicleMaintenance<br />PlanAssignment. 
| [StartingDate](Applications.Fleet.VehicleMaintenancePlanAssignments.md#startingdate) | date | The date on which the periodic maintenance should start.[Required] [Filter(ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenancePlan](Applications.Fleet.VehicleMaintenancePlanAssignments.md#maintenanceplan) | [MaintenancePlans](Applications.Fleet.MaintenancePlans.md) | The assigned periodic maintenance type. |
| [Vehicle](Applications.Fleet.VehicleMaintenancePlanAssignments.md#vehicle) | [Vehicles](Applications.Fleet.Vehicles.md) | The vehicle, to which a periodic maintenance plan is assigned. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.VehicleMaintenancePlanAssignments.md#id) | guid |  
| [ObjectVersion](Applications.Fleet.VehicleMaintenancePlanAssignments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Fleet.VehicleMaintenancePlanAssignments.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Fleet.VehicleMaintenancePlanAssignments.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Fleet.VehicleMaintenancePlanAssignments.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Fleet.VehicleMaintenancePlanAssignments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

Specifies whether the plan is active.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### LastMaintenanceMileageKm

The mileage of the vehicle (in Kilometers), when the last maintenance of this type occurred. Should be specified for plans, which require mileage check.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LastMaintenanceTripCount

The trip count of the vehicle, when the last maintenance of this type occurred. Should be specified for plans, which trip count check.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this VehicleMaintenancePlanAssignment.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### StartingDate

The date on which the periodic maintenance should start.[Required] [Filter(ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### MaintenancePlan

The assigned periodic maintenance type.

Type: **[MaintenancePlans](Applications.Fleet.MaintenancePlans.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Vehicle

The vehicle, to which a periodic maintenance plan is assigned.

Type: **[Vehicles](Applications.Fleet.Vehicles.md)**  
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

[!list limit=1000 erp.entity=Applications.Fleet.VehicleMaintenancePlanAssignments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.VehicleMaintenancePlanAssignments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Fleet_VehicleMaintenancePlanAssignments

Domain API Entity Type: 
Applications_Fleet_VehicleMaintenancePlanAssignment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Fleet_VehicleMaintenancePlanAssignments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Fleet_VehicleMaintenancePlanAssignments?$top=10>

