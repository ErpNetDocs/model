---
uid: Applications.Fleet.MaintenanceProfilePlans
---
# Applications.Fleet.MaintenanceProfilePlans


Contains the plans, included in the maintenance profile.

## General
Namespace: [Applications.Fleet](Applications.Fleet.md)  
Repository: Applications.Fleet.MaintenanceProfilePlans  
Base Table: Fleet_Maintenance_Profile_Plans  
API access:  ReadWrite  

## Visualization
Display Format: {MaintenanceProfile.Name}  
Search Members: MaintenanceProfile.Name  
Name Member: MaintenanceProfile.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Fleet.MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md)  
Aggregate Root:  
[Applications.Fleet.MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Applications.Fleet.MaintenanceProfilePlans.md#isactive) | boolean | 1 if the maintenance plan is active for this profile. When a plan is not active, maintenance for it will not occur for the current profile.[Required] [Default(true)] [Introduced in version 18.2] 
| [Notes](Applications.Fleet.MaintenanceProfilePlans.md#notes) | string (max) __nullable__ | Notes for this MaintenanceProfilePlan. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenancePlan](Applications.Fleet.MaintenanceProfilePlans.md#maintenanceplan) | [MaintenancePlans](Applications.Fleet.MaintenancePlans.md) | The maintenance plan, which is included in the profile. |
| [MaintenanceProfile](Applications.Fleet.MaintenanceProfilePlans.md#maintenanceprofile) | [MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) | The maintenance profile, which includes the plan. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.MaintenanceProfilePlans.md#id) | guid |  
| [ObjectVersion](Applications.Fleet.MaintenanceProfilePlans.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Fleet.MaintenanceProfilePlans.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

1 if the maintenance plan is active for this profile. When a plan is not active, maintenance for it will not occur for the current profile.[Required] [Default(true)] [Introduced in version 18.2]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this MaintenanceProfilePlan.

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
Show in UI: **ShownByDefault**  

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

### MaintenancePlan

The maintenance plan, which is included in the profile.

Type: **[MaintenancePlans](Applications.Fleet.MaintenancePlans.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MaintenanceProfile

The maintenance profile, which includes the plan.

Type: **[MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md)**  
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

[!list limit=1000 erp.entity=Applications.Fleet.MaintenanceProfilePlans erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.MaintenanceProfilePlans erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Fleet_MaintenanceProfilePlans

Domain API Entity Type: 
Applications_Fleet_MaintenanceProfilePlan

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Fleet_MaintenanceProfilePlans?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Fleet_MaintenanceProfilePlans?$top=10>

