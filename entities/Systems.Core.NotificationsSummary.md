---
uid: Systems.Core.NotificationsSummary
---
# Systems.Core.NotificationsSummary View

**Namespace:** [Systems.Core](Systems.Core.md)  

Summary info for notifications, grouped by user and data object. Entity: Cmm_Notifications_Summary_View (Introduced in version 25.1.1.20)

## Default Visualization
Default Display Text Format:  
_{DataObjectId}: {UserId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

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

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### LastNotificationId

The id of the last notification, related to this data object. `Required` `Filter(multi eq)` `Introduced in version 25.1.3.61`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LastNotificationSubject

The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)` `Inherited from Cmm_Notifications_Table.Subject`

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Inherited From_: **Cmm_Notifications_Table.Subject**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### LastNotificationTime

The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `Inherited from Cmm_Notifications_Table.Creation_Time_Utc`

_Type_: **datetime**  
_Category_: **System**  
_Inherited From_: **Cmm_Notifications_Table.Creation_Time_Utc**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

### NotificationsCount

Notifications Count. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### NotReadCount

Not Read Count. `Required` `Filter(eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DataObject

The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.Data_Object_Id`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Cmm_Notifications_Table.Data_Object_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user, who is notified. `Required` `Filter(multi eq)` `Inherited from Cmm_Notifications_Table.User_Id`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Inherited From_: **Cmm_Notifications_Table.User_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set:
Systems_Core_NotificationsSummary

Domain API Entity Type:
Systems_Core_NotificationsSummary

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_NotificationsSummary?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_NotificationsSummary?$top=10>

