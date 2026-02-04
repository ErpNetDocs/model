---
uid: Crm.Pos.Terminals
---
# Crm.Pos.Terminals


Represents a POS workplace for 1 person, with all the attached devices. (Not to be confused with Payment Terminal, which is specific POS device)

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.Terminals  
Base Table: Pos_Terminals  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {PosTerminalName:T}  
Search Members: PosTerminalCode; PosTerminalName  
Code Member: PosTerminalCode  
Name Member: PosTerminalName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  2 - Track object changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.Terminals](Crm.Pos.Terminals.md)  
  * [Crm.Pos.Devices](Crm.Pos.Devices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Crm.Pos.Terminals.md#isactive) | boolean | Represents whether the POS terminal is active and can be chosen from drop-downs for new records. `Required` `Default(true)` `Filter(multi eq)` 
| [PosTerminalCode](Crm.Pos.Terminals.md#posterminalcode) | string (16) | Unique (within the location) code of the POS terminal. `Required` `Filter(eq;like)` 
| [PosTerminalName](Crm.Pos.Terminals.md#posterminalname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The multi-language name of the terminal, like "Cash 1", "Self-checkout 5", etc. `Required` `Filter(multi eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultFiscalPrinter<br />PosDevice](Crm.Pos.Terminals.md#defaultfiscalprinterposdevice) | [Devices](Crm.Pos.Devices.md) (nullable) | The POS Fiscal Device which is set by default in documents when the POS Terminal is selected. `Filter(multi eq)` `Introduced in version 20.1` |
| [PosLocation](Crm.Pos.Terminals.md#poslocation) | [Locations](Crm.Pos.Locations.md) | The POS location, where the terminal is located. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.Terminals.md#id) | guid |  
| [ObjectVersion](Crm.Pos.Terminals.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.Terminals.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.Terminals.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.Terminals.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.Terminals.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Devices | [Devices](Crm.Pos.Devices.md) | List of `Device`(Crm.Pos.Devices.md) child objects, based on the `Crm.Pos.Device.PosTerminal`(Crm.Pos.Devices.md#posterminal) back reference 


## Attribute Details

### IsActive

Represents whether the POS terminal is active and can be chosen from drop-downs for new records. `Required` `Default(true)` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### PosTerminalCode

Unique (within the location) code of the POS terminal. `Required` `Filter(eq;like)`

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PosTerminalName

The multi-language name of the terminal, like "Cash 1", "Self-checkout 5", etc. `Required` `Filter(multi eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
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

### DefaultFiscalPrinterPosDevice

The POS Fiscal Device which is set by default in documents when the POS Terminal is selected. `Filter(multi eq)` `Introduced in version 20.1`

Type: **[Devices](Crm.Pos.Devices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosLocation

The POS location, where the terminal is located. `Required` `Filter(multi eq)`

Type: **[Locations](Crm.Pos.Locations.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Crm.Pos.Terminals erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.Terminals erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_Terminals

Domain API Entity Type: 
Crm_Pos_Terminal

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_Terminals?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_Terminals?$top=10>

