---
uid: Systems.Monitoring.UserPresence
---
# Systems.Monitoring.UserPresence View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Tracks user availability and status changes in real time. Entity: Dmv_User_Presence (Introduced in version 25.1.2.51)

## Default Visualization
Default Display Text Format:  
_{UserId}: {UserLogin}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.UserPresence](Systems.Monitoring.UserPresence.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LastUpdateTimeUtc](Systems.Monitoring.UserPresence.md#lastupdatetimeutc) | datetime | Timestamp (UTC) of the last status update. `Required` `Filter(ge;le)` `ORD` 
| [Status](Systems.Monitoring.UserPresence.md#status) | string (5) | The user's current presence status. `Required` `Filter(multi eq)` 
| [UserId](Systems.Monitoring.UserPresence.md#userid) | guid | Unique identifier for the user. `Required` `Filter(multi eq)` 
| [UserLogin](Systems.Monitoring.UserPresence.md#userlogin) | string (64) | The username used to log in. `Required` `Filter(multi eq;like)` 


## Attribute Details

### LastUpdateTimeUtc

Timestamp (UTC) of the last status update. `Required` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Status

The user's current presence status. `Required` `Filter(multi eq)`

_Type_: **string (5)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **5**  
_Show in UI_: **ShownByDefault**  

### UserId

Unique identifier for the user. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UserLogin

The username used to log in. `Required` `Filter(multi eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_UserPresence?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_UserPresence?$top=10>

