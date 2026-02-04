---
uid: Applications.Fleet.TripSegments
---
# Applications.Fleet.TripSegments


Represents the segments which comprise the route of the trips

## General
Namespace: [Applications.Fleet](Applications.Fleet.md)  
Repository: Applications.Fleet.TripSegments  
Base Table: Fleet_Trip_Segments  
API access:  ReadWrite  

## Visualization
Display Format: {Trip.EntityName}  
Search Members: Trip.EntityName  
Name Member: Trip.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Fleet.Trips](Applications.Fleet.Trips.md)  
Aggregate Root:  
[Applications.Fleet.Trips](Applications.Fleet.Trips.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndingTimestamp](Applications.Fleet.TripSegments.md#endingtimestamp) | datetime __nullable__ | The ending date and time of the travel on the segment. `Filter(ge;le)` 
| [Mileage](Applications.Fleet.TripSegments.md#mileage) | decimal (9, 0) __nullable__ | Mileage of the route segment. The mileage is measured in the operational units of the vehicle even when it is not miles or kilometers. null means unknown mileage. 
| [Notes](Applications.Fleet.TripSegments.md#notes) | string (254) __nullable__ | Notes for the segment. 
| [StartingTimestamp](Applications.Fleet.TripSegments.md#startingtimestamp) | datetime | The starting date and time of the travel on the segment. `Required` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EndingMapPoint](Applications.Fleet.TripSegments.md#endingmappoint) | [MapPoints](General.Geography.MapPoints.md) | The ending geographical point of the route segment. `Required` `Filter(multi eq)` |
| [StartingMapPoint](Applications.Fleet.TripSegments.md#startingmappoint) | [MapPoints](General.Geography.MapPoints.md) | The starting geographical point of the route segment. `Required` `Filter(multi eq)` |
| [Trip](Applications.Fleet.TripSegments.md#trip) | [Trips](Applications.Fleet.Trips.md) | The trip for which the segment is defined. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.TripSegments.md#id) | guid |  
| [ObjectVersion](Applications.Fleet.TripSegments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Fleet.TripSegments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EndingTimestamp

The ending date and time of the travel on the segment. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Mileage

Mileage of the route segment. The mileage is measured in the operational units of the vehicle even when it is not miles or kilometers. null means unknown mileage.

Type: **decimal (9, 0) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the segment.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### StartingTimestamp

The starting date and time of the travel on the segment. `Required` `Filter(ge;le)`

Type: **datetime**  
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

### EndingMapPoint

The ending geographical point of the route segment. `Required` `Filter(multi eq)`

Type: **[MapPoints](General.Geography.MapPoints.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StartingMapPoint

The starting geographical point of the route segment. `Required` `Filter(multi eq)`

Type: **[MapPoints](General.Geography.MapPoints.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Trip

The trip for which the segment is defined. `Required` `Filter(multi eq)` `Owner`

Type: **[Trips](Applications.Fleet.Trips.md)**  
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

[!list limit=1000 erp.entity=Applications.Fleet.TripSegments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.TripSegments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Fleet_TripSegments

Domain API Entity Type: 
Applications_Fleet_TripSegment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Fleet_TripSegments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Fleet_TripSegments?$top=10>

