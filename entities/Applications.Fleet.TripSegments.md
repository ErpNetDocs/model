---
uid: Applications.Fleet.TripSegments
---
# Applications.Fleet.TripSegments Entity

**Namespace:** [Applications.Fleet](Applications.Fleet.md)  

Represents the segments which comprise the route of the trips. Entity: Fleet_Trip_Segments

## Default Visualization
Default Display Text Format:  
_{Trip.EntityName}_  
Default Search Members:  
_Trip.EntityName_  
Name Data Member:  
_Trip.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Fleet.Trips](Applications.Fleet.Trips.md)  
Aggregate Root:  
[Applications.Fleet.Trips](Applications.Fleet.Trips.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Fleet.TripSegments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndingTimestamp](Applications.Fleet.TripSegments.md#endingtimestamp) | datetime __nullable__ | The ending date and time of the travel on the segment. `Filter(ge;le)` 
| [Id](Applications.Fleet.TripSegments.md#id) | guid |  
| [Mileage](Applications.Fleet.TripSegments.md#mileage) | decimal (9, 0) __nullable__ | Mileage of the route segment. The mileage is measured in the operational units of the vehicle even when it is not miles or kilometers. null means unknown mileage. 
| [Notes](Applications.Fleet.TripSegments.md#notes) | string (254) __nullable__ | Notes for the segment. 
| [ObjectVersion](Applications.Fleet.TripSegments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartingTimestamp](Applications.Fleet.TripSegments.md#startingtimestamp) | datetime | The starting date and time of the travel on the segment. `Required` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EndingMapPoint](Applications.Fleet.TripSegments.md#endingmappoint) | [MapPoints](General.Geography.MapPoints.md) | The ending geographical point of the route segment. `Required` `Filter(multi eq)` |
| [StartingMapPoint](Applications.Fleet.TripSegments.md#startingmappoint) | [MapPoints](General.Geography.MapPoints.md) | The starting geographical point of the route segment. `Required` `Filter(multi eq)` |
| [Trip](Applications.Fleet.TripSegments.md#trip) | [Trips](Applications.Fleet.Trips.md) | The trip for which the segment is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EndingTimestamp

The ending date and time of the travel on the segment. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Mileage

Mileage of the route segment. The mileage is measured in the operational units of the vehicle even when it is not miles or kilometers. null means unknown mileage.

_Type_: **decimal (9, 0) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the segment.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartingTimestamp

The starting date and time of the travel on the segment. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EndingMapPoint

The ending geographical point of the route segment. `Required` `Filter(multi eq)`

_Type_: **[MapPoints](General.Geography.MapPoints.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### StartingMapPoint

The starting geographical point of the route segment. `Required` `Filter(multi eq)`

_Type_: **[MapPoints](General.Geography.MapPoints.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Trip

The trip for which the segment is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Trips](Applications.Fleet.Trips.md)**  
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

