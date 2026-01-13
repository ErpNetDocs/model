---
uid: Systems.Security.UserDevices
---
# Systems.Security.UserDevices Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

Information about devices linked to users, including login activity, and notification preferences for each device. Entity: Sec_User_Devices (Introduced in version 1.0.0.25)

## Default Visualization
Default Display Text Format:  
_{DeviceName}_  
Default Search Members:  
_DeviceName_  
Name Data Member:  
_DeviceName_  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Users](Systems.Security.Users.md)  
Aggregate Root:  
[Systems.Security.Users](Systems.Security.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Systems.Security.UserDevices.md#creationtimeutc) | datetime | The exact server time (in UTC), when the device was registered. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.2.30` 
| [DeviceFingerprint](Systems.Security.UserDevices.md#devicefingerprint) | string (2048) __nullable__ | A unique identifier for the device based on its fingerprint, used to track devices securely. This column can be null if not provided. `Filter(eq)` `ReadOnly` `Introduced in version 25.1.2.30` 
| [DeviceInfo](Systems.Security.UserDevices.md#deviceinfo) | string (4092) __nullable__ | Shows basic information about your device. `ReadOnly` `Introduced in version 25.1.2.34` 
| [DeviceName](Systems.Security.UserDevices.md#devicename) | string (256) | The name of the device, such as the model or a custom name given by the user. `Required` `Introduced in version 25.1.2.30` 
| [DisplayText](Systems.Security.UserDevices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Security.UserDevices.md#id) | guid |  
| [LastLoginTimeUtc](Systems.Security.UserDevices.md#lastlogintimeutc) | datetime | The exact server time (in UTC) when the device was last used to sign in. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` `Introduced in version 25.1.2.30` 
| [NotificationsAllowed](Systems.Security.UserDevices.md#notificationsallowed) | boolean | Тhe device is allowed to receive notifications from the system. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.2.30` 
| [NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem) | [NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem) | The type or system of notifications allowed on the device, typically referring to the notification service (e.g., FCM, WebPush, etc.). `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.2.30` 
| [NotificationsToken](Systems.Security.UserDevices.md#notificationstoken) | string (2048) __nullable__ | A token used for sending notifications to the device, such as a push notification token. null if not applicable. `ReadOnly` `Introduced in version 25.1.2.30` 
| [ObjectVersion](Systems.Security.UserDevices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Security.UserDevices.md#user) | [Users](Systems.Security.Users.md) | The <see cref="User"/> to which this UserDevice belongs. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.30` `Owner` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the device was registered. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.2.30`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### DeviceFingerprint

A unique identifier for the device based on its fingerprint, used to track devices securely. This column can be null if not provided. `Filter(eq)` `ReadOnly` `Introduced in version 25.1.2.30`

_Type_: **string (2048) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **2048**  
_Show in UI_: **ShownByDefault**  

### DeviceInfo

Shows basic information about your device. `ReadOnly` `Introduced in version 25.1.2.34`

_Type_: **string (4092) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **4092**  
_Show in UI_: **ShownByDefault**  

### DeviceName

The name of the device, such as the model or a custom name given by the user. `Required` `Introduced in version 25.1.2.30`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
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
_Show in UI_: **ShownByDefault**  

### LastLoginTimeUtc

The exact server time (in UTC) when the device was last used to sign in. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` `Introduced in version 25.1.2.30`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### NotificationsAllowed

Тhe device is allowed to receive notifications from the system. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.2.30`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### NotificationsSystem

The type or system of notifications allowed on the device, typically referring to the notification service (e.g., FCM, WebPush, etc.). `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.2.30`

_Type_: **[NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem)**  
_Category_: **System**  
Allowed values for the `NotificationsSystem`(Systems.Security.UserDevices.md#notificationssystem) data attribute  
_Allowed Values (Systems.Security.UserDevicesRepository.NotificationsSystem Enum Members)_  

| Value | Description |
| ---- | --- |
| NotAvailable | No notification system available for the device.. Stored as 'NA'. <br /> _Database Value:_ 'NA' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NotAvailable' |
| FirebaseCloudMessaging | Google service for sending notifications across platforms.. Stored as 'FCM'. <br /> _Database Value:_ 'FCM' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'FirebaseCloudMessaging' |
| WebPushAPI | Push notifications for web browsers.. Stored as 'WPUSH'. <br /> _Database Value:_ 'WPUSH' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'WebPushAPI' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### NotificationsToken

A token used for sending notifications to the device, such as a push notification token. null if not applicable. `ReadOnly` `Introduced in version 25.1.2.30`

_Type_: **string (2048) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2048**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### User

The <see cref="User"/> to which this UserDevice belongs. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.30` `Owner`

_Type_: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Systems.Security.UserDevices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.UserDevices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_UserDevices

Domain API Entity Type: 
Systems_Security_UserDevice

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_UserDevices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_UserDevices?$top=10>

