---
uid: Applications.AssetManagement.ManagedAssets
---
# Applications.AssetManagement.ManagedAssets


Contains the managed assets. The management of assets include maintenance planning and execution, location assignments tracking, etc.

## General
Namespace: [Applications.AssetManagement](Applications.AssetManagement.md)  
Repository: Applications.AssetManagement.ManagedAssets  
Base Table: Eam_Managed_Assets  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  ManagedAssetTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  
  * [Applications.AssetManagement.ManagedAssetLinks](Applications.AssetManagement.ManagedAssetLinks.md)  
  * [Applications.AssetManagement.ManagedAssetLocations](Applications.AssetManagement.ManagedAssetLocations.md)  
  * [Applications.AssetManagement.ManagedAssetMaintenanceSchedules](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md)  
  * [Applications.AssetManagement.ManagedAssetParameterValues](Applications.AssetManagement.ManagedAssetParameterValues.md)  
  * [Applications.AssetManagement.ManagedAssetScheduledMaintenances](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Applications.AssetManagement.ManagedAssets.md#code) | string (16) | Unique code of the managed asset. The code is unique among all managed assets in the same enterprise company. `Required` `Filter(eq;like)` 
| [IsActive](Applications.AssetManagement.ManagedAssets.md#isactive) | boolean | Indicates whether the current Managed Asset is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.1.73` 
| [Name](Applications.AssetManagement.ManagedAssets.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the managed asset (multi-language). `Required` `Filter(eq;like)` 
| [Notes](Applications.AssetManagement.ManagedAssets.md#notes) | string (max) __nullable__ | Notes for this ManagedAsset. 
| [RegistrationNumber](Applications.AssetManagement.ManagedAssets.md#registrationnumber) | string (32) __nullable__ | Registration number of the asset with the national registration authorities. null means the registation number is unknown or N/A. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.AssetManagement.ManagedAssets.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company to which the managed asset belongs. `Filter(multi eq)` |
| [FixedAsset](Applications.AssetManagement.ManagedAssets.md#fixedasset) | [Assets](Finance.Assets.Assets.md) (nullable) | The currently managed fixed asset. null means that no fixed asset is currently managed. `Filter(multi eq)` `Introduced in version 25.1.1.93` |
| [ManagedAssetGroup](Applications.AssetManagement.ManagedAssets.md#managedassetgroup) | [ManagedAssetGroups](Applications.AssetManagement.ManagedAssetGroups.md) | The organizational group of the asset. Used for organizational purposes only. `Required` `Filter(multi eq)` |
| [ManagedAssetType](Applications.AssetManagement.ManagedAssets.md#managedassettype) | [ManagedAssetTypes](Applications.AssetManagement.ManagedAssetTypes.md) | The type of the asset. Determines the tracked parameters for the asset, the applicable maintenance types, etc. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssets.md#id) | guid |  
| [ObjectVersion](Applications.AssetManagement.ManagedAssets.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.AssetManagement.ManagedAssets.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.AssetManagement.ManagedAssets.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.AssetManagement.ManagedAssets.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.AssetManagement.ManagedAssets.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Links | [ManagedAssetLinks](Applications.AssetManagement.ManagedAssetLinks.md) | List of `ManagedAssetLink`(Applications.AssetManagement.ManagedAssetLinks.md) child objects, based on the `Applications.AssetManagement.ManagedAssetLink.ManagedAsset`(Applications.AssetManagement.ManagedAssetLinks.md#managedasset) back reference 
| Locations | [ManagedAssetLocations](Applications.AssetManagement.ManagedAssetLocations.md) | List of `ManagedAssetLocation`(Applications.AssetManagement.ManagedAssetLocations.md) child objects, based on the `Applications.AssetManagement.ManagedAssetLocation.ManagedAsset`(Applications.AssetManagement.ManagedAssetLocations.md#managedasset) back reference 
| MaintenanceSchedules | [ManagedAssetMaintenanceSchedules](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md) | List of `ManagedAssetMaintenance<br />Schedule`(Applications.AssetManagement.ManagedAssetMaintenance<br />Schedules.md) child objects, based on the `Applications.AssetManagement.ManagedAssetMaintenance<br />Schedule.ManagedAsset`(Applications.AssetManagement.ManagedAssetMaintenance<br />Schedules.md#managedasset) back reference 
| ParameterValues | [ManagedAssetParameterValues](Applications.AssetManagement.ManagedAssetParameterValues.md) | List of `ManagedAssetParameter<br />Value`(Applications.AssetManagement.ManagedAssetParameter<br />Values.md) child objects, based on the `Applications.AssetManagement.ManagedAssetParameterValue.ManagedAsset`(Applications.AssetManagement.ManagedAssetParameter<br />Values.md#managedasset) back reference 
| ScheduledMaintenances | [ManagedAssetScheduledMaintenances](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md) | List of `ManagedAssetScheduled<br />Maintenance`(Applications.AssetManagement.ManagedAssetScheduled<br />Maintenances.md) child objects, based on the `Applications.AssetManagement.ManagedAssetScheduled<br />Maintenance.ManagedAsset`(Applications.AssetManagement.ManagedAssetScheduled<br />Maintenances.md#managedasset) back reference 


## Attribute Details

### Code

Unique code of the managed asset. The code is unique among all managed assets in the same enterprise company. `Required` `Filter(eq;like)`

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Managed Asset is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.1.73`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the managed asset (multi-language). `Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ManagedAsset.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RegistrationNumber

Registration number of the asset with the national registration authorities. null means the registation number is unknown or N/A. `Filter(eq;like)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **32**  
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

The enterprise company to which the managed asset belongs. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### FixedAsset

The currently managed fixed asset. null means that no fixed asset is currently managed. `Filter(multi eq)` `Introduced in version 25.1.1.93`

Type: **[Assets](Finance.Assets.Assets.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAssetGroup

The organizational group of the asset. Used for organizational purposes only. `Required` `Filter(multi eq)`

Type: **[ManagedAssetGroups](Applications.AssetManagement.ManagedAssetGroups.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAssetType

The type of the asset. Determines the tracked parameters for the asset, the applicable maintenance types, etc. `Required` `Filter(multi eq)`

Type: **[ManagedAssetTypes](Applications.AssetManagement.ManagedAssetTypes.md)**  
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

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssets erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssets erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_ManagedAssets

Domain API Entity Type: 
Applications_AssetManagement_ManagedAsset

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssets?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssets?$top=10>

