---
uid: General.Resources.ResourceAvailability
---
# General.Resources.ResourceAvailability


Contains the resources availability for the different periods. Each period is a separate record. The availability of a resource for any given date is determined by the sum of all availability periods that include it.

## General
Namespace: [General.Resources](General.Resources.md)  
Repository: General.Resources.ResourceAvailability  
Base Table: Gen_Resource_Availability  
API access:  ReadWrite  

## Visualization
Display Format: {Resource.Name:T}  
Search Members: Resource.Name  
Name Member: Resource.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Resources.Resources](General.Resources.Resources.md)  
Aggregate Root:  
[General.Resources.ResourceGroups](General.Resources.ResourceGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvailableResources](General.Resources.ResourceAvailability.md#availableresources) | decimal (12, 2) | The quantity of the resource, available for the specified period. For non-discrete resources, this number can contain fractions. When several availability periods for a resource overlap, the total availability is the sum of all. 
| [FromDate](General.Resources.ResourceAvailability.md#fromdate) | date | The date from which availability starts. 
| [ToDate](General.Resources.ResourceAvailability.md#todate) | date __nullable__ | The date to which the availability continues. When NULL, the availability continues infinitely. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Resource](General.Resources.ResourceAvailability.md#resource) | [Resources](General.Resources.Resources.md) | The resource, for which we provide availability. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Resources.ResourceAvailability.md#id) | guid |  
| [ObjectVersion](General.Resources.ResourceAvailability.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Resources.ResourceAvailability.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AvailableResources

The quantity of the resource, available for the specified period. For non-discrete resources, this number can contain fractions. When several availability periods for a resource overlap, the total availability is the sum of all.

Type: **decimal (12, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### FromDate

The date from which availability starts.

Type: **date**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

The date to which the availability continues. When NULL, the availability continues infinitely.

Type: **date __nullable__**  
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

### Resource

The resource, for which we provide availability.

Type: **[Resources](General.Resources.Resources.md)**  
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

[!list limit=1000 erp.entity=General.Resources.ResourceAvailability erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Resources.ResourceAvailability erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Resources_ResourceAvailability

Domain API Entity Type: 
General_Resources_ResourceAvailability

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Resources_ResourceAvailability?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Resources_ResourceAvailability?$top=10>

