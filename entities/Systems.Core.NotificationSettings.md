---
uid: Systems.Core.NotificationSettings
---
# Systems.Core.NotificationSettings


User notification settings for the different notification classes.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.NotificationSettings  
Base Table: Cmm_Notification_Settings  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Renames

Old name: Communities.NotificationSettings  
New name: Systems.Core.NotificationSettings  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Id}: {UserId}  
Search Members:   
Category:  Definitions  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.NotificationSettings](Systems.Core.NotificationSettings.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [NotificationClass](Systems.Core.NotificationSettings.md#notificationclass) | string (64) __nullable__ | The class of the notification, for which the user is specifying settings. When NULL, the setting is applied to all notification classes.[Filter(multi eq)] 
| [ReceiveDeviceNotification](Systems.Core.NotificationSettings.md#receivedevicenotification) | boolean | True if the user should receive device notification.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.2.34] 
| [ReceiveMail](Systems.Core.NotificationSettings.md#receivemail) | boolean | True if the user should receive mail.[Required] [Default(false)] [Filter(eq)] 
| [ReceiveNotification](Systems.Core.NotificationSettings.md#receivenotification) | boolean | True if the user should receive internal notification.[Required] [Default(true)] [Filter(eq)] 
| [ReceiveSms](Systems.Core.NotificationSettings.md#receivesms) | boolean | True if the user should receive SMS.[Required] [Default(false)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Core.NotificationSettings.md#user) | [Users](Systems.Security.Users.md) | The user for whom the notification setting is about. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.NotificationSettings.md#id) | guid |  
| [ObjectVersion](Systems.Core.NotificationSettings.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.NotificationSettings.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.NotificationSettings.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.NotificationSettings.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.NotificationSettings.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### NotificationClass

The class of the notification, for which the user is specifying settings. When NULL, the setting is applied to all notification classes.[Filter(multi eq)]

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ReceiveDeviceNotification

True if the user should receive device notification.[Required] [Default(true)] [Filter(eq)] [Introduced in version 25.1.2.34]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### ReceiveMail

True if the user should receive mail.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ReceiveNotification

True if the user should receive internal notification.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### ReceiveSms

True if the user should receive SMS.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
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

### User

The user for whom the notification setting is about.

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Systems.Core.NotificationSettings erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.NotificationSettings erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_NotificationSettings

Domain API Entity Type: 
Systems_Core_NotificationSetting

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_NotificationSettings?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_NotificationSettings?$top=10>

