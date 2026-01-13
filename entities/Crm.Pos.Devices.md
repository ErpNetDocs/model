---
uid: Crm.Pos.Devices
---
# Crm.Pos.Devices Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Represents one POS device, attached to a POS terminal. Entity: Pos_Devices (Introduced in version 19.1)

## Default Visualization
Default Display Text Format:  
_{PosTerminal.PosTerminalName:T}_  
Default Search Members:  
_PosTerminal.PosTerminalName_  
Name Data Member:  
_PosTerminal.PosTerminalName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pos.Terminals](Crm.Pos.Terminals.md)  
Aggregate Root:  
[Crm.Pos.Terminals](Crm.Pos.Terminals.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeviceRegistrationNo](Crm.Pos.Devices.md#deviceregistrationno) | string (32) __nullable__ | The unique registration number of the device, assigned by the manufacturer. null means the number is unknown or N/A. `Filter(multi eq;like)` 
| [DeviceType](Crm.Pos.Devices.md#devicetype) | [DeviceType](Crm.Pos.Devices.md#devicetype) | Type of the POS device. PAY=Payment Terminal; CSH=Cash Drawer; FIP=Fiscal Printer; OTH=Other. `Required` `Default("OTH")` `Filter(multi eq)` 
| [DisplayText](Crm.Pos.Devices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ElectronicAddress](Crm.Pos.Devices.md#electronicaddress) | string (254) __nullable__ | The absolute address (Internet or other) which can be used for electronic communication with the device. The address should contain communication protocol/type, colon, space, then the actual address. Addresses, which are local to a specific computer, should also include the computer name. For example: "COM: PC_WORK1:COM1", "HTTP: https://&lt;addr&gt;", etc. `Filter(multi eq;like)` 
| [Id](Crm.Pos.Devices.md#id) | guid |  
| [IsActive](Crm.Pos.Devices.md#isactive) | boolean | Indicates whether the device is currently active and can be choosen from drop-downs in new records. `Required` `Default(true)` `Filter(multi eq)` 
| [ObjectVersion](Crm.Pos.Devices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProtocolName](Crm.Pos.Devices.md#protocolname) | [ProtocolName](Crm.Pos.Devices.md#protocolname) __nullable__ | The name of the protocol, which can be used to communicate with the device. null means that the protocol is unknown and programmatic communication with the device would not be performed. 
| [SettingsJson](Crm.Pos.Devices.md#settingsjson) | string (max) __nullable__ | Settings and operator access codes for the POS device. The data is stored as Json, encrypted for the current application server instance. null means that there are no settings for this device. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PosTerminal](Crm.Pos.Devices.md#posterminal) | [Terminals](Crm.Pos.Terminals.md) | The POS terminal, to which this device is attached. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DeviceRegistrationNo

The unique registration number of the device, assigned by the manufacturer. null means the number is unknown or N/A. `Filter(multi eq;like)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DeviceType

Type of the POS device. PAY=Payment Terminal; CSH=Cash Drawer; FIP=Fiscal Printer; OTH=Other. `Required` `Default("OTH")` `Filter(multi eq)`

_Type_: **[DeviceType](Crm.Pos.Devices.md#devicetype)**  
_Category_: **System**  
Allowed values for the `DeviceType`(Crm.Pos.Devices.md#devicetype) data attribute  
_Allowed Values (Crm.Pos.DevicesRepository.DeviceType Enum Members)_  

| Value | Description |
| ---- | --- |
| PaymentTerminal | PaymentTerminal value. Stored as 'PAY'. <br /> _Database Value:_ 'PAY' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'PaymentTerminal' |
| CashDrawer | CashDrawer value. Stored as 'CSH'. <br /> _Database Value:_ 'CSH' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CashDrawer' |
| FiscalPrinter | FiscalPrinter value. Stored as 'FIP'. <br /> _Database Value:_ 'FIP' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FiscalPrinter' |
| Other | Other value. Stored as 'OTH'. <br /> _Database Value:_ 'OTH' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Other**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ElectronicAddress

The absolute address (Internet or other) which can be used for electronic communication with the device. The address should contain communication protocol/type, colon, space, then the actual address. Addresses, which are local to a specific computer, should also include the computer name. For example: "COM: PC_WORK1:COM1", "HTTP: https://&lt;addr&gt;", etc. `Filter(multi eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the device is currently active and can be choosen from drop-downs in new records. `Required` `Default(true)` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProtocolName

The name of the protocol, which can be used to communicate with the device. null means that the protocol is unknown and programmatic communication with the device would not be performed.

_Type_: **[ProtocolName](Crm.Pos.Devices.md#protocolname) __nullable__**  
_Category_: **System**  
Allowed values for the `ProtocolName`(Crm.Pos.Devices.md#protocolname) data attribute  
_Allowed Values (Crm.Pos.DevicesRepository.ProtocolName Enum Members)_  

| Value | Description |
| ---- | --- |
| ERPNETFP | ErpNet.FP. Stored as 'ERPNET_FP'. <br /> _Database Value:_ 'ERPNET_FP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ERPNETFP' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SettingsJson

Settings and operator access codes for the POS device. The data is stored as Json, encrypted for the current application server instance. null means that there are no settings for this device.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### PosTerminal

The POS terminal, to which this device is attached. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Terminals](Crm.Pos.Terminals.md)**  
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

