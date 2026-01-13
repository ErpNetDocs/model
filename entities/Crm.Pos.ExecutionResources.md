---
uid: Crm.Pos.ExecutionResources
---
# Crm.Pos.ExecutionResources Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Defines physical or logical resources used to execute services or fulfill POS Sale Lines. This includes tables in a restaurant, rooms in a salon or clinic, training stations in a gym, or equipment in a workshop. Entity: Pos_Execution_Resources (Introduced in version 25.1.3.45)

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
| [Capacity](Crm.Pos.ExecutionResources.md#capacity) | int32 __nullable__ | Optional: number of simultaneous uses (e.g., seating for 4). `Filter(eq;ge;le)` 
| [Code](Crm.Pos.ExecutionResources.md#code) | string (16) | Unique (within the location) code of the resource. Used for display constrained devices, import/export matching, etc. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Crm.Pos.ExecutionResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pos.ExecutionResources.md#id) | guid |  
| [IsActive](Crm.Pos.ExecutionResources.md#isactive) | boolean | Indicates whether the POS execution resource  is currently active. `Required` `Default(true)` `Filter(eq)` 
| [Name](Crm.Pos.ExecutionResources.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Human readable resource name, e.g. "Table 5", "Room 58". `Required` `Filter(like)` 
| [Notes](Crm.Pos.ExecutionResources.md#notes) | string (max) __nullable__ | Notes for the execution resource. `Filter(like)` 
| [ObjectVersion](Crm.Pos.ExecutionResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Area](Crm.Pos.ExecutionResources.md#area) | [LocationAreas](Crm.Pos.LocationAreas.md) (nullable) | Area (zone) within the POS location, where the resource is located. `Filter(multi eq)` |
| [Location](Crm.Pos.ExecutionResources.md#location) | [Locations](Crm.Pos.Locations.md) | The POS location where the resource is situated. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Capacity

Optional: number of simultaneous uses (e.g., seating for 4). `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Code

Unique (within the location) code of the resource. Used for display constrained devices, import/export matching, etc. `Required` `Filter(eq;like)` `ORD`

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

Indicates whether the POS execution resource  is currently active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Human readable resource name, e.g. "Table 5", "Room 58". `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for the execution resource. `Filter(like)`

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


## Reference Details

### Area

Area (zone) within the POS location, where the resource is located. `Filter(multi eq)`

_Type_: **[LocationAreas](Crm.Pos.LocationAreas.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Location

The POS location where the resource is situated. `Required` `Filter(multi eq)` `Owner`

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

