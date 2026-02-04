---
uid: General.Activities.ActivityResources
---
# General.Activities.ActivityResources


Contains the resources, allocated to the activities.

## General
Namespace: [General.Activities](General.Activities.md)  
Repository: General.Activities.ActivityResources  
Base Table: Cm_Activity_Resources  
API access:  ReadWrite  

## Renames

Old name: General.Contacts.ActivityResources  
New name: General.Activities.ActivityResources  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Activity.EntityName}  
Search Members: Activity.EntityName  
Name Member: Activity.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Activities.Activities](General.Activities.Activities.md)  
Aggregate Root:  
[General.Activities.Activities](General.Activities.Activities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Notes](General.Activities.ActivityResources.md#notes) | string (255) __nullable__ | Notes for this ActivityResource. 
| [ResourceUsagePercent](General.Activities.ActivityResources.md#resourceusagepercent) | decimal (18, 4) | The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](General.Activities.ActivityResources.md#activity) | [Activities](General.Activities.Activities.md) | The <see cref="Activity"/> to which this ActivityResource belongs. `Required` `Filter(multi eq)` `Owner` |
| [Resource](General.Activities.ActivityResources.md#resource) | [Resources](General.Resources.Resources.md) | The resource, which is required by the activity. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Activities.ActivityResources.md#id) | guid |  
| [ObjectVersion](General.Activities.ActivityResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Activities.ActivityResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Notes

Notes for this ActivityResource.

Type: **string (255) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **255**  
Show in UI: **ShownByDefault**  

### ResourceUsagePercent

The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required.

Type: **decimal (18, 4)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
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

### Activity

The <see cref="Activity"/> to which this ActivityResource belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Activities](General.Activities.Activities.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Resource

The resource, which is required by the activity.

Type: **[Resources](General.Resources.Resources.md)**  
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

[!list limit=1000 erp.entity=General.Activities.ActivityResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Activities.ActivityResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Activities_ActivityResources

Domain API Entity Type: 
General_Activities_ActivityResource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Activities_ActivityResources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Activities_ActivityResources?$top=10>

