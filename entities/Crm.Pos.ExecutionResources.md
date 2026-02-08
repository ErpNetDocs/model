---
uid: Crm.Pos.ExecutionResources
---
# Crm.Pos.ExecutionResources


Defines physical or logical resources used to execute services or fulfill POS Sale Lines. This includes tables in a restaurant, rooms in a salon or clinic, training stations in a gym, or equipment in a workshop.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.ExecutionResources  
Base Table: Pos_Execution_Resources  
Introduced In Version: 25.1.3.45  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  
Aggregate Root:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Capacity](Crm.Pos.ExecutionResources.md#capacity) | int32 __nullable__ | Optional: number of simultaneous uses (e.g., seating for 4)`Filter(eq;ge;le)` 
| [Code](Crm.Pos.ExecutionResources.md#code) | string (16) | Unique (within the location) code of the resource. Used for display constrained devices, import/export matching, etc.`Required` `Filter(eq;like)` `ORD` 
| [IsActive](Crm.Pos.ExecutionResources.md#isactive) | boolean | Indicates whether the POS execution resource is currently active.`Required` `Default(true)` `Filter(eq)` 
| [Name](Crm.Pos.ExecutionResources.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Human readable resource name, e.g. 'Table 5', 'Room 58'.`Required` `Filter(like)` 
| [Notes](Crm.Pos.ExecutionResources.md#notes) | string (max) __nullable__ | Notes for the execution resource.`Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Area](Crm.Pos.ExecutionResources.md#area) | [LocationAreas](Crm.Pos.LocationAreas.md) (nullable) | Area (zone) within the POS location, where the resource is located. |
| [Location](Crm.Pos.ExecutionResources.md#location) | [Locations](Crm.Pos.Locations.md) | The POS location where the resource is situated. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.ExecutionResources.md#id) | guid |  
| [ObjectVersion](Crm.Pos.ExecutionResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pos.ExecutionResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Capacity

Optional: number of simultaneous uses (e.g., seating for 4)`Filter(eq;ge;le)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Code

Unique (within the location) code of the resource. Used for display constrained devices, import/export matching, etc.`Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the POS execution resource is currently active.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Human readable resource name, e.g. 'Table 5', 'Room 58'.`Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the execution resource.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### Area

Area (zone) within the POS location, where the resource is located.

Type: **[LocationAreas](Crm.Pos.LocationAreas.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Location

The POS location where the resource is situated.

Type: **[Locations](Crm.Pos.Locations.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.ExecutionResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ExecutionResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_ExecutionResources

Domain API Entity Type: 
Crm_Pos_ExecutionResource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_ExecutionResources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_ExecutionResources?$top=10>

