---
uid: Applications.AssetManagement.ManagedAssetMaintenanceSchedules
---
# Applications.AssetManagement.ManagedAssetMaintenanceSchedules


Contains the maintenance schedules for the managed assets.

## General
Namespace: [Applications.AssetManagement](Applications.AssetManagement.md)  
Repository: Applications.AssetManagement.ManagedAssetMaintenanceSchedules  
Base Table: Eam_Managed_Asset_Maintenance_Schedules  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {ManagedAsset.Name:T}  
Search Members: ManagedAsset.Name  
Name Member: ManagedAsset.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  
Aggregate Root:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Notes](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#notes) | string (max) __nullable__ | Notes for this ManagedAssetMaintenance<br />Schedule. 
| [ParameterChangeDelta](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#parameterchangedelta) | int32 __nullable__ | The value of the tracked parameter change between planned maintenances. The tracked parameter is determined based on the Maintenance Type. null means, that the maintenances are not planned, based on parameter change. `Filter(multi eq;ge;le)` 
| [ScheduleDays](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#scheduledays) | int32 __nullable__ | Number of days between planned maintenances. null means that the schedule is not planned based on days. 
| [ScheduleMonths](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#schedulemonths) | int32 __nullable__ | Number of months between planned maintenances. null means that the schedule is not planned based on months. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenanceType](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#maintenancetype) | [MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | What type of maintenance is scheduled. `Required` `Filter(multi eq)` |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The managed asset for which the maintenance schedule applies. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#id) | guid |  
| [ObjectVersion](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Notes

Notes for this ManagedAssetMaintenanceSchedule.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ParameterChangeDelta

The value of the tracked parameter change between planned maintenances. The tracked parameter is determined based on the Maintenance Type. null means, that the maintenances are not planned, based on parameter change. `Filter(multi eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScheduleDays

Number of days between planned maintenances. null means that the schedule is not planned based on days.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScheduleMonths

Number of months between planned maintenances. null means that the schedule is not planned based on months.

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

### MaintenanceType

What type of maintenance is scheduled. `Required` `Filter(multi eq)`

Type: **[MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

The managed asset for which the maintenance schedule applies. `Required` `Filter(multi eq)` `Owner`

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
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

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetMaintenanceSchedules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetMaintenanceSchedules erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_ManagedAssetMaintenanceSchedules

Domain API Entity Type: 
Applications_AssetManagement_ManagedAssetMaintenanceSchedule

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetMaintenanceSchedules?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetMaintenanceSchedules?$top=10>

