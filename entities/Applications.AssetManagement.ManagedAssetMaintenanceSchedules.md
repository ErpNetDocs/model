---
uid: Applications.AssetManagement.ManagedAssetMaintenanceSchedules
---
# Applications.AssetManagement.ManagedAssetMaintenanceSchedules Entity

**Namespace:** [Applications.AssetManagement](Applications.AssetManagement.md)  

Contains the maintenance schedules for the managed assets. Entity: Eam_Managed_Asset_Maintenance_Schedules (Introduced in version 19.1)

## Default Visualization
Default Display Text Format:  
_{ManagedAsset.Name:T}_  
Default Search Members:  
_ManagedAsset.Name_  
Name Data Member:  
_ManagedAsset.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  
Aggregate Root:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#id) | guid |  
| [Notes](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#notes) | string (max) __nullable__ | Notes for this ManagedAssetMaintenance<br />Schedule. 
| [ObjectVersion](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParameterChangeDelta](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#parameterchangedelta) | int32 __nullable__ | The value of the tracked parameter change between planned maintenances. The tracked parameter is determined based on the Maintenance Type. null means, that the maintenances are not planned, based on parameter change. `Filter(multi eq;ge;le)` 
| [ScheduleDays](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#scheduledays) | int32 __nullable__ | Number of days between planned maintenances. null means that the schedule is not planned based on days. 
| [ScheduleMonths](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#schedulemonths) | int32 __nullable__ | Number of months between planned maintenances. null means that the schedule is not planned based on months. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenanceType](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#maintenancetype) | [MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | What type of maintenance is scheduled. `Required` `Filter(multi eq)` |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The managed asset for which the maintenance schedule applies. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

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

### Notes

Notes for this ManagedAssetMaintenanceSchedule.

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

### ParameterChangeDelta

The value of the tracked parameter change between planned maintenances. The tracked parameter is determined based on the Maintenance Type. null means, that the maintenances are not planned, based on parameter change. `Filter(multi eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ScheduleDays

Number of days between planned maintenances. null means that the schedule is not planned based on days.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ScheduleMonths

Number of months between planned maintenances. null means that the schedule is not planned based on months.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### MaintenanceType

What type of maintenance is scheduled. `Required` `Filter(multi eq)`

_Type_: **[MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ManagedAsset

The managed asset for which the maintenance schedule applies. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
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

