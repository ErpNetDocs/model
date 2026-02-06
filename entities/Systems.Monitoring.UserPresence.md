---
uid: Systems.Monitoring.UserPresence
---
# Systems.Monitoring.UserPresence (View)


Tracks user availability and status changes in real time

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.UserPresence  
Introduced In Version: 25.1.2.51  
API access:  ReadWrite  

## Visualization
Display Format: {UserId}: {UserLogin}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.UserPresence](Systems.Monitoring.UserPresence.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LastUpdateTimeUtc](Systems.Monitoring.UserPresence.md#lastupdatetimeutc) | datetime | Timestamp (UTC) of the last status update.[Required] [Filter(ge;le)] [ORD] [ReadOnly] 
| [Status](Systems.Monitoring.UserPresence.md#status) | [Status](Systems.Monitoring.UserPresence.md#status) | The user's current presence status.[Required] [Filter(multi eq)] [ReadOnly] 
| [UserId](Systems.Monitoring.UserPresence.md#userid) | guid | Unique identifier for the user. `Required` `Filter(multi eq)` `ReadOnly` 
| [UserLogin](Systems.Monitoring.UserPresence.md#userlogin) | string (64) | The username used to log in.[Required] [Filter(multi eq;like)] [ReadOnly] 


## Attribute Details

### LastUpdateTimeUtc

Timestamp (UTC) of the last status update.[Required] [Filter(ge;le)] [ORD] [ReadOnly]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Status

The user's current presence status.[Required] [Filter(multi eq)] [ReadOnly]

Type: **[Status](Systems.Monitoring.UserPresence.md#status)**  
Category: **System**  
Allowed values for the `Status`(Systems.Monitoring.UserPresence.md#status) data attribute  
Allowed Values (Systems.Monitoring.UserPresenceRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| Available | The user is available and does not fall into any other category.. Stored as 'AVLB'. <br /> Database Value: 'AVLB' <br /> Model Value: 0 <br /> Domain API Value: 'Available' |
| DoNotDisturb | The user has manually set their status to 'Do Not Disturb'.. Stored as 'DND'. <br /> Database Value: 'DND' <br /> Model Value: 1 <br /> Domain API Value: 'DoNotDisturb' |
| Busy | The user has a scheduled meeting in the calendar for this period. Can also be set manually.. Stored as 'BUSY'. <br /> Database Value: 'BUSY' <br /> Model Value: 2 <br /> Domain API Value: 'Busy' |
| Away | The user is logged in but has been inactive for the last 5 minutes.. Stored as 'AWAY'. <br /> Database Value: 'AWAY' <br /> Model Value: 3 <br /> Domain API Value: 'Away' |
| Offline | The user is not logged into the system.. Stored as 'OFFLN'. <br /> Database Value: 'OFFLN' <br /> Model Value: 4 <br /> Domain API Value: 'Offline' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UserId

Unique identifier for the user. `Required` `Filter(multi eq)` `ReadOnly`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UserLogin

The username used to log in.[Required] [Filter(multi eq;like)] [ReadOnly]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_UserPresence

Domain API Entity Type: 
Systems_Monitoring_UserPresenceEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_UserPresence?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_UserPresence?$top=10>

