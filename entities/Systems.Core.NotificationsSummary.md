---
uid: Systems.Core.NotificationsSummary
---
# Systems.Core.NotificationsSummary (View)


Summary info for notifications, grouped by user and data object.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.NotificationsSummary  
Introduced In Version: 25.1.1.20  
API access:  ReadWrite  

## Visualization
Display Format: {DataObjectId}: {UserId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.NotificationsSummary](Systems.Core.NotificationsSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LastNotificationClass](Systems.Core.NotificationsSummary.md#lastnotificationclass) | string (64) | Last Notification Class. `Required` `Introduced in version 25.1.1.34` 
| [LastNotificationId](Systems.Core.NotificationsSummary.md#lastnotificationid) | guid | The id of the last notification, related to this data object. `Required` `Filter(multi eq)` `Introduced in version 25.1.3.61` 
| [LastNotificationSubject](Systems.Core.NotificationsSummary.md#lastnotificationsubject) | string (256) __nullable__ | The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)` `Inherited from Cmm_Notifications_Table.Subject` 
| [LastNotificationTime](Systems.Core.NotificationsSummary.md#lastnotificationtime) | datetime | The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `Inherited from Cmm_Notifications_Table.Creation_Time_Utc` 
| [NotificationsCount](Systems.Core.NotificationsSummary.md#notificationscount) | int32 | Notifications Count. `Required` 
| [NotReadCount](Systems.Core.NotificationsSummary.md#notreadcount) | int32 | Not Read Count. `Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Systems.Core.NotificationsSummary.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.Data_Object_Id` |
| [User](Systems.Core.NotificationsSummary.md#user) | [Users](Systems.Security.Users.md) | The user, who is notified. `Required` `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.User_Id` |


## Attribute Details

### LastNotificationClass

Last Notification Class. `Required` `Introduced in version 25.1.1.34`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### LastNotificationId

The id of the last notification, related to this data object. `Required` `Filter(multi eq)` `Introduced in version 25.1.3.61`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LastNotificationSubject

The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)` `Inherited from Cmm_Notifications_Table.Subject`

Type: **string (256) __nullable__**  
Category: **System**  
Inherited From: **Cmm_Notifications_Table.Subject**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### LastNotificationTime

The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `Inherited from Cmm_Notifications_Table.Creation_Time_Utc`

Type: **datetime**  
Category: **System**  
Inherited From: **Cmm_Notifications_Table.Creation_Time_Utc**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### NotificationsCount

Notifications Count. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NotReadCount

Not Read Count. `Required` `Filter(eq;ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### DataObject

The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.Data_Object_Id`

Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
Category: **System**  
Inherited From: **Cmm_Notifications_Table.Data_Object_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, who is notified. `Required` `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.User_Id`

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Inherited From: **Cmm_Notifications_Table.User_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Core_NotificationsSummary

Domain API Entity Type: 
Systems_Core_NotificationsSummary

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_NotificationsSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_NotificationsSummary?$top=10>

