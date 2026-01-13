---
uid: Crm.Pos.LocationAreas
---
# Crm.Pos.LocationAreas Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Defines logical zones, sections, or areas within a broader shop, restaurant, clinic, gym, or service facility. Each area groups together multiple execution resources (e.g., tables, rooms, equipment) and is used for resource organization, routing, display grouping, and service assignment. Examples include "Main Dining Room", "Terrace", "Kitchen", or "Bar". Entity: Pos_Location_Areas (Introduced in version 25.1.3.45)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  
Aggregate Root:  
[Crm.Pos.Locations](Crm.Pos.Locations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Crm.Pos.LocationAreas.md#code) | string (16) | Unique (within the location) short code, e.g., DINING, ZONE-A. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Crm.Pos.LocationAreas.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pos.LocationAreas.md#id) | guid |  
| [IsActive](Crm.Pos.LocationAreas.md#isactive) | boolean | Indicates whether the POS location area  is currently active. `Required` `Default(true)` `Filter(eq)` 
| [Name](Crm.Pos.LocationAreas.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | User-friendly name (e.g., "Main Dining Hall"). `Required` `Filter(like)` 
| [Notes](Crm.Pos.LocationAreas.md#notes) | string (max) __nullable__ | Notes for the location area. `Filter(like)` 
| [ObjectVersion](Crm.Pos.LocationAreas.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](Crm.Pos.LocationAreas.md#ord) | int32 | Sort order within the location. Controls display order in UI components. `Required` `Filter(eq;ge;le)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Location](Crm.Pos.LocationAreas.md#location) | [Locations](Crm.Pos.Locations.md) | Parent shop, salon or facility. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Code

Unique (within the location) short code, e.g., DINING, ZONE-A. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

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

### IsActive

Indicates whether the POS location area  is currently active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

User-friendly name (e.g., "Main Dining Hall"). `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the location area. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### Ord

Sort order within the location. Controls display order in UI components. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Location.Areas.Select( c => c.Ord).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`obj.SetLocationAreaOrd( obj.Location)`
`( obj.Location.Areas.Select( c => c.Ord).DefaultIfEmpty( 0).Max( ) + 1)`

## Reference Details

### Location

Parent shop, salon or facility. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Locations](Crm.Pos.Locations.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.LocationAreas erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.LocationAreas erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_LocationAreas

Domain API Entity Type: 
Crm_Pos_LocationArea

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_LocationAreas?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_LocationAreas?$top=10>

