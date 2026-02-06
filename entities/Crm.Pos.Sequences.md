---
uid: Crm.Pos.Sequences
---
# Crm.Pos.Sequences


Stores the last issued fiscal sales number for each POS device.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.Sequences  
Base Table: Pos_Sequences  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {PosSequenceName:T}  
Search Members: PosSequenceName  
Name Member: PosSequenceName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  2 - Track object changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.Sequences](Crm.Pos.Sequences.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Crm.Pos.Sequences.md#isactive) | boolean | Indicates whether this sequence is active.[Required] [Default(true)] [Filter(multi eq)] 
| [MaxNo](Crm.Pos.Sequences.md#maxno) | string (16) __nullable__ | Specifies the maximum number allowed in the sequence. NULL means that the sequence will grow unlimited.[Filter(multi eq;ge;le)] 
| [NextNo](Crm.Pos.Sequences.md#nextno) | string (16) | The next consecutive number which will be assigned on the next request.[Required] [Filter(multi eq;ge;le)] 
| [PosSequenceName](Crm.Pos.Sequences.md#possequencename) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The multi-language name of the sequence.[Filter(multi eq;like)] [Introduced in version 26.2.1.28] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PosDevice](Crm.Pos.Sequences.md#posdevice) | [Devices](Crm.Pos.Devices.md) (nullable) | The POS device, for which the sequence is defined. |
| [PosLocation](Crm.Pos.Sequences.md#poslocation) | [Locations](Crm.Pos.Locations.md) (nullable) | The POS location, for which the sequence is defined. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.Sequences.md#id) | guid |  
| [ObjectVersion](Crm.Pos.Sequences.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.Sequences.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.Sequences.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.Sequences.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.Sequences.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

Indicates whether this sequence is active.[Required] [Default(true)] [Filter(multi eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### MaxNo

Specifies the maximum number allowed in the sequence. NULL means that the sequence will grow unlimited.[Filter(multi eq;ge;le)]

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### NextNo

The next consecutive number which will be assigned on the next request.[Required] [Filter(multi eq;ge;le)]

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PosSequenceName

The multi-language name of the sequence.[Filter(multi eq;like)] [Introduced in version 26.2.1.28]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
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

### PosDevice

The POS device, for which the sequence is defined.

Type: **[Devices](Crm.Pos.Devices.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosLocation

The POS location, for which the sequence is defined.

Type: **[Locations](Crm.Pos.Locations.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pos.Sequences erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.Sequences erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_Sequences

Domain API Entity Type: 
Crm_Pos_Sequence

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_Sequences?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_Sequences?$top=10>

