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
| [LastUpdateTimeUtc](Systems.Monitoring.UserPresence.md#lastupdatetimeutc) | datetime | Timestamp (UTC) of the last status update. `Required` `Filter(ge;le)` `ORD` `ReadOnly` 
| [Status](Systems.Monitoring.UserPresence.md#status) | [Status](Systems.Monitoring.UserPresence.md#status) | The user's current presence status. `Required` `Filter(multi eq)` `ReadOnly` 
| [UserId](Systems.Monitoring.UserPresence.md#userid) | guid | Unique identifier for the user. `Required` `Filter(multi eq)` `ReadOnly` 
| [UserLogin](Systems.Monitoring.UserPresence.md#userlogin) | string (64) | The username used to log in. `Required` `Filter(multi eq;like)` `ReadOnly` 


## Attribute Details

### LastUpdateTimeUtc

Timestamp (UTC) of the last status update. `Required` `Filter(ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Status

The user's current presence status. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Status](Systems.Monitoring.UserPresence.md#status)**  
_Category_: **System**  
Allowed values for the `Status`(Systems.Monitoring.UserPresence.md#status) data attribute  
_Allowed Values (Systems.Monitoring.UserPresenceRepository.Status Enum Members)_  

| Value | Description |
| ---- | --- |
| Offline | The user is not logged into the system.. Stored as 'OFFLN'. <br /> _Database Value:_ 'OFFLN' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Offline' |
| Available | The user is available and does not fall into any other category.. Stored as 'AVLB'. <br /> _Database Value:_ 'AVLB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Available' |
| Away | The user is logged in but has been inactive for the last 5 minutes.. Stored as 'AWAY'. <br /> _Database Value:_ 'AWAY' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Away' |
| InCall | The user is currently in a video call.. Stored as 'CALL'. <br /> _Database Value:_ 'CALL' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'InCall' |
| InMeeting | The user is in a scheduled meeting as per the calendar. Stored as 'MEET'. <br /> _Database Value:_ 'MEET' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'InMeeting' |
| Busy | The user has a scheduled meeting in the calendar for this period. Can also be set manually.. Stored as 'BUSY'. <br /> _Database Value:_ 'BUSY' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Busy' |
| DoNotDisturb | The user has manually set their status to 'Do Not Disturb'.. Stored as 'DND'. <br /> _Database Value:_ 'DND' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'DoNotDisturb' |
| Presenting | The user is actively sharing their screen.. Stored as 'PRSNT'. <br /> _Database Value:_ 'PRSNT' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Presenting' |
| BeRightBack | The user has manually set their status to 'Be Right Back'.. Stored as 'BRB'. <br /> _Database Value:_ 'BRB' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'BeRightBack' |
| OutOfOffice | OutOfOffice. Stored as 'OOO'. <br /> _Database Value:_ 'OOO' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'OutOfOffice' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UserId

Unique identifier for the user. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UserLogin

The username used to log in. `Required` `Filter(multi eq;like)` `ReadOnly`

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

