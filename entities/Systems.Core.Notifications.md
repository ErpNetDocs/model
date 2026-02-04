---
uid: Systems.Core.Notifications
---
# Systems.Core.Notifications


A single notification of a user.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.Notifications  
Base Table: Cmm_Notifications  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Renames

Old name: Communities.Notifications  
New name: Systems.Core.Notifications  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Id}: {UserId}  
Search Members: Subject  
Category:  Definitions  
Show in UI:  HiddenByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.Notifications](Systems.Core.Notifications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Anchor](Systems.Core.Notifications.md#anchor) | string (128) __nullable__ | A custom reference (most commonly a relative URL) pointing to an additional resource related to the DataObject. `Introduced in version 25.1.1.3` 
| [CreationTimeUtc](Systems.Core.Notifications.md#creationtimeutc) | datetime | The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` 
| [IsRead](Systems.Core.Notifications.md#isread) | boolean | Specifies whether the user has read the notification. If the system changes the notification after first reading, the flag is reset to unread again. `Required` `Default(false)` `Filter(eq)` 
| [NotificationClass](Systems.Core.Notifications.md#notificationclass) | string (64) | The class of the notification from a predefined list of system classes. `Required` `Filter(multi eq)` 
| [Priority](Systems.Core.Notifications.md#priority) | [Priority](Systems.Core.Notifications.md#priority) | Indicates the importance level of the notification, helping determine its order of attention or urgency. `Required` `Default(3)` `Filter(eq;ge;le)` `Introduced in version 25.1.2.63` 
| [Subject](Systems.Core.Notifications.md#subject) | string (256) __nullable__ | The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Systems.Core.Notifications.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)` |
| [User](Systems.Core.Notifications.md#user) | [Users](Systems.Security.Users.md) | The user, who is notified. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.Notifications.md#id) | guid |  
| [ObjectVersion](Systems.Core.Notifications.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Core.Notifications.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Core.Notifications.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Core.Notifications.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Core.Notifications.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Anchor

A custom reference (most commonly a relative URL) pointing to an additional resource related to the DataObject. `Introduced in version 25.1.1.3`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### CreationTimeUtc

The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### IsRead

Specifies whether the user has read the notification. If the system changes the notification after first reading, the flag is reset to unread again. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### NotificationClass

The class of the notification from a predefined list of system classes. `Required` `Filter(multi eq)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Priority

Indicates the importance level of the notification, helping determine its order of attention or urgency. `Required` `Default(3)` `Filter(eq;ge;le)` `Introduced in version 25.1.2.63`

Type: **[Priority](Systems.Core.Notifications.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Background | Background value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
| Low | Low value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
| Normal | Normal value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
| High | High value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'High' |
| Urgent | Urgent value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **3**  
Show in UI: **ShownByDefault**  

### Subject

The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)`

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **256**  
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

### DataObject

The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)`

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, who is notified. `Required` `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Systems.Core.Notifications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.Notifications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_Notifications

Domain API Entity Type: 
Systems_Core_Notification

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_Notifications?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_Notifications?$top=10>

