---
uid: Applications.AssetManagement.ManagedAssetScheduledMaintenances
---
# Applications.AssetManagement.ManagedAssetScheduledMaintenances


Contains the scheduled maintenances for the managed assets. Each maintenance can be planned based on date, parameter value or both. Past maintenance plans are kept only for reference and can be deleted at any time.

## General
Namespace: [Applications.AssetManagement](Applications.AssetManagement.md)  
Repository: Applications.AssetManagement.ManagedAssetScheduledMaintenances  
Base Table: Eam_Managed_Asset_Scheduled_Maintenances  
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
| [Date](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#date) | date __nullable__ | The date, when the maintenance is planned. NULL means, that the plan is not related to date, but to tracked parameter value. If both date and parameter are specified, the maintenance is performed when any of the conditions is met.[Filter(multi eq;ge;le)] 
| [IsDismissed](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#isdismissed) | boolean | Specifies whether the notification for the maintenance is dismissed and the planner has decided the course of action.[Required] [Default(false)] [Filter(multi eq)] 
| [Notes](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#notes) | string (max) __nullable__ | Notes for this ManagedAssetScheduled<br />Maintenance. 
| [TrackedParameterValue](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#trackedparametervalue) | int32 __nullable__ | The value of the tracked parameter (as specified in the maintenance type) at which the maintenance will be performed. For example, for a car, we can schedule maintenance at 20,000 km mileage. NULL means, that the maintenance is not planned based on parameter, but rather only for date. If both date and parameter are specified, the maintenance is performed when any of the conditions is met.[Filter(multi eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenanceType](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#maintenancetype) | [MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | The type of maintenance, which will be performed. |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The asset, which will be maintained. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#id) | guid |  
| [ObjectVersion](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Date

The date, when the maintenance is planned. NULL means, that the plan is not related to date, but to tracked parameter value. If both date and parameter are specified, the maintenance is performed when any of the conditions is met.[Filter(multi eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsDismissed

Specifies whether the notification for the maintenance is dismissed and the planner has decided the course of action.[Required] [Default(false)] [Filter(multi eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ManagedAssetScheduledMaintenance.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### TrackedParameterValue

The value of the tracked parameter (as specified in the maintenance type) at which the maintenance will be performed. For example, for a car, we can schedule maintenance at 20,000 km mileage. NULL means, that the maintenance is not planned based on parameter, but rather only for date. If both date and parameter are specified, the maintenance is performed when any of the conditions is met.[Filter(multi eq;ge;le)]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

The type of maintenance, which will be performed.

Type: **[MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

The asset, which will be maintained.

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

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetScheduledMaintenances erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetScheduledMaintenances erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_ManagedAssetScheduledMaintenances

Domain API Entity Type: 
Applications_AssetManagement_ManagedAssetScheduledMaintenance

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetScheduledMaintenances?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetScheduledMaintenances?$top=10>

