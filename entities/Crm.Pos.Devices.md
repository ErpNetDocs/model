---
uid: Crm.Pos.Devices
---
# Crm.Pos.Devices


Represents one POS device, attached to a POS terminal.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.Devices  
Base Table: Pos_Devices  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Visualization
Display Format: {PosTerminal.PosTerminalName:T}  
Search Members: PosTerminal.PosTerminalName  
Name Member: PosTerminal.PosTerminalName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Terminals](Crm.Pos.Terminals.md)  
Aggregate Root:  
[Crm.Pos.Terminals](Crm.Pos.Terminals.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeviceRegistrationNo](Crm.Pos.Devices.md#deviceregistrationno) | string (32) __nullable__ | The unique registration number of the device, assigned by the manufacturer. NULL means the number is unknown or N/A. 
| [DeviceType](Crm.Pos.Devices.md#devicetype) | [DeviceType](Crm.Pos.Devices.md#devicetype) | Type of the POS device. PAY=Payment Terminal; CSH=Cash Drawer; FIP=Fiscal Printer; OTH=Other. 
| [ElectronicAddress](Crm.Pos.Devices.md#electronicaddress) | string (254) __nullable__ | The absolute address (Internet or other) which can be used for electronic communication with the device. The address should contain communication protocol/type, colon, space, then the actual address. Addresses, which are local to a specific computer, should also include the computer name. For example: "COM: PC_WORK1:COM1", "HTTP: https://<addr>", etc. 
| [IsActive](Crm.Pos.Devices.md#isactive) | boolean | Indicates whether the device is currently active and can be choosen from drop-downs in new records. 
| [ProtocolName](Crm.Pos.Devices.md#protocolname) | [ProtocolName](Crm.Pos.Devices.md#protocolname) __nullable__ | The name of the protocol, which can be used to communicate with the device. NULL means that the protocol is unknown and programmatic communication with the device would not be performed. 
| [SettingsJson](Crm.Pos.Devices.md#settingsjson) | string (max) __nullable__ | Settings and operator access codes for the POS device. The data is stored as Json, encrypted for the current application server instance. NULL means that there are no settings for this device. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PosTerminal](Crm.Pos.Devices.md#posterminal) | [Terminals](Crm.Pos.Terminals.md) | The POS terminal, to which this device is attached. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.Devices.md#id) | guid |  
| [ObjectVersion](Crm.Pos.Devices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pos.Devices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DeviceRegistrationNo

The unique registration number of the device, assigned by the manufacturer. NULL means the number is unknown or N/A.

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### DeviceType

Type of the POS device. PAY=Payment Terminal; CSH=Cash Drawer; FIP=Fiscal Printer; OTH=Other.

Type: **[DeviceType](Crm.Pos.Devices.md#devicetype)**  
Category: **System**  
Allowed values for the `DeviceType`(Crm.Pos.Devices.md#devicetype) data attribute  
Allowed Values (Crm.Pos.DevicesRepository.DeviceType Enum Members)  

| Value | Description |
| ---- | --- |
| PaymentTerminal | PaymentTerminal value. Stored as 'PAY'. <br /> Database Value: 'PAY' <br /> Model Value: 0 <br /> Domain API Value: 'PaymentTerminal' |
| CashDrawer | CashDrawer value. Stored as 'CSH'. <br /> Database Value: 'CSH' <br /> Model Value: 1 <br /> Domain API Value: 'CashDrawer' |
| FiscalPrinter | FiscalPrinter value. Stored as 'FIP'. <br /> Database Value: 'FIP' <br /> Model Value: 2 <br /> Domain API Value: 'FiscalPrinter' |
| Other | Other value. Stored as 'OTH'. <br /> Database Value: 'OTH' <br /> Model Value: 3 <br /> Domain API Value: 'Other' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Other**  
Show in UI: **ShownByDefault**  

### ElectronicAddress

The absolute address (Internet or other) which can be used for electronic communication with the device. The address should contain communication protocol/type, colon, space, then the actual address. Addresses, which are local to a specific computer, should also include the computer name. For example: "COM: PC_WORK1:COM1", "HTTP: https://<addr>", etc.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the device is currently active and can be choosen from drop-downs in new records.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### ProtocolName

The name of the protocol, which can be used to communicate with the device. NULL means that the protocol is unknown and programmatic communication with the device would not be performed.

Type: **[ProtocolName](Crm.Pos.Devices.md#protocolname) __nullable__**  
Category: **System**  
Allowed values for the `ProtocolName`(Crm.Pos.Devices.md#protocolname) data attribute  
Allowed Values (Crm.Pos.DevicesRepository.ProtocolName Enum Members)  

| Value | Description |
| ---- | --- |
| ERPNETFP | ErpNet.FP. Stored as 'ERPNET_FP'. <br /> Database Value: 'ERPNET_FP' <br /> Model Value: 0 <br /> Domain API Value: 'ERPNETFP' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SettingsJson

Settings and operator access codes for the POS device. The data is stored as Json, encrypted for the current application server instance. NULL means that there are no settings for this device.

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

### PosTerminal

The POS terminal, to which this device is attached.

Type: **[Terminals](Crm.Pos.Terminals.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.Devices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.Devices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_Devices

Domain API Entity Type: 
Crm_Pos_Device

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_Devices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_Devices?$top=10>

