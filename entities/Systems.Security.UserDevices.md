---
uid: Systems.Security.UserDevices
---
# Systems.Security.UserDevices


Information about devices linked to users, including login activity, and notification preferences for each device.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.UserDevices  
Base Table: Sec_User_Devices  
Introduced In Version: 1.0.0.25  
API access:  ReadWrite  

## Visualization
Display Format: {DeviceName}  
Search Members: DeviceName  
Name Member: DeviceName  
Category:  Definitions  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

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
| [LastLoginTimeUtc](Systems.Security.UserDevices.md#lastlogintimeutc) | datetime | The exact server time (in UTC) when the device was last used to sign in. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` `Introduced in version 25.1.2.30` 
| [NotificationsAllowed](Systems.Security.UserDevices.md#notificationsallowed) | boolean | Тhe device is allowed to receive notifications from the system. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.2.30` 
| [NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem) | [NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem) | The type or system of notifications allowed on the device, typically referring to the notification service (e.g., FCM, WebPush, etc.). `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.2.30` 
| [NotificationsToken](Systems.Security.UserDevices.md#notificationstoken) | string (2048) __nullable__ | A token used for sending notifications to the device, such as a push notification token. null if not applicable. `ReadOnly` `Introduced in version 25.1.2.30` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Security.UserDevices.md#user) | [Users](Systems.Security.Users.md) | The <see cref="User"/> to which this UserDevice belongs. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.30` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.UserDevices.md#id) | guid |  
| [ObjectVersion](Systems.Security.UserDevices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.UserDevices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the device was registered. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.2.30`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### DeviceFingerprint

A unique identifier for the device based on its fingerprint, used to track devices securely. This column can be null if not provided. `Filter(eq)` `ReadOnly` `Introduced in version 25.1.2.30`

Type: **string (2048) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **2048**  
Show in UI: **ShownByDefault**  

### DeviceInfo

Shows basic information about your device. `ReadOnly` `Introduced in version 25.1.2.34`

Type: **string (4092) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **4092**  
Show in UI: **ShownByDefault**  

### DeviceName

The name of the device, such as the model or a custom name given by the user. `Required` `Introduced in version 25.1.2.30`

Type: **string (256)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### LastLoginTimeUtc

The exact server time (in UTC) when the device was last used to sign in. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` `Introduced in version 25.1.2.30`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### NotificationsAllowed

Тhe device is allowed to receive notifications from the system. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.2.30`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### NotificationsSystem

The type or system of notifications allowed on the device, typically referring to the notification service (e.g., FCM, WebPush, etc.). `Required` `Filter(multi eq)` `ReadOnly` `Introduced in version 25.1.2.30`

Type: **[NotificationsSystem](Systems.Security.UserDevices.md#notificationssystem)**  
Category: **System**  
Allowed values for the `NotificationsSystem`(Systems.Security.UserDevices.md#notificationssystem) data attribute  
Allowed Values (Systems.Security.UserDevicesRepository.NotificationsSystem Enum Members)  

| Value | Description |
| ---- | --- |
| NotAvailable | No notification system available for the device.. Stored as 'NA'. <br /> Database Value: 'NA' <br /> Model Value: 0 <br /> Domain API Value: 'NotAvailable' |
| FirebaseCloudMessaging | Google service for sending notifications across platforms.. Stored as 'FCM'. <br /> Database Value: 'FCM' <br /> Model Value: 1 <br /> Domain API Value: 'FirebaseCloudMessaging' |
| WebPushAPI | Push notifications for web browsers.. Stored as 'WPUSH'. <br /> Database Value: 'WPUSH' <br /> Model Value: 2 <br /> Domain API Value: 'WebPushAPI' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NotificationsToken

A token used for sending notifications to the device, such as a push notification token. null if not applicable. `ReadOnly` `Introduced in version 25.1.2.30`

Type: **string (2048) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2048**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Show in UI: **ShownByDefault**  

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

### User

The <see cref="User"/> to which this UserDevice belongs. `Required` `Filter(multi eq)` `Introduced in version 25.1.2.30` `Owner`

Type: **[Users](Systems.Security.Users.md)**  
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

