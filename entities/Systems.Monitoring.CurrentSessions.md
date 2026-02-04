---
uid: Systems.Monitoring.CurrentSessions
---
# Systems.Monitoring.CurrentSessions (View)


Shows the current sessions to the database.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.CurrentSessions  
Introduced In Version: 23.1.1.52  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.CurrentSessions  
New name: Systems.Monitoring.CurrentSessions  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {SessionId}: {UserLogin}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.CurrentSessions](Systems.Monitoring.CurrentSessions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AbsoluteExpirationTime](Systems.Monitoring.CurrentSessions.md#absoluteexpirationtime) | datetime | Absolute expiration time of the session. Not empty if the session is created by a service appllication. `Required` `Filter(ge;le)` `ORD` 
| [Applications](Systems.Monitoring.CurrentSessions.md#applications) | string (64) | A comma separated list of client applications that share this session. `Required` `Filter(eq;like)` `ORD` 
| [CurrentRequestsCount](Systems.Monitoring.CurrentSessions.md#currentrequestscount) | int32 | The requests count in the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [Device](Systems.Monitoring.CurrentSessions.md#device) | string (64) | The name of the user's device. `Required` `Filter(eq;like)` `ORD` 
| [DownloadMB](Systems.Monitoring.CurrentSessions.md#downloadmb) | decimal (12, 3) | The downloaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [LastRequestTime](Systems.Monitoring.CurrentSessions.md#lastrequesttime) | datetime | The last request time. `Required` `Filter(ge;le)` `ORD` 
| [SessionId](Systems.Monitoring.CurrentSessions.md#sessionid) | string (64) | The id of the session. `Required` `Filter(eq)` `Introduced in version 26.1.4.3` 
| [StartTime](Systems.Monitoring.CurrentSessions.md#starttime) | datetime | The login time of the session. `Required` `Filter(ge;le)` `ORD` 
| [TotalRequestsCount](Systems.Monitoring.CurrentSessions.md#totalrequestscount) | int64 | The total request count at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [UploadMB](Systems.Monitoring.CurrentSessions.md#uploadmb) | decimal (12, 3) | The uploaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [UserLogin](Systems.Monitoring.CurrentSessions.md#userlogin) | string (64) | The user login name. `Required` `Introduced in version 26.1.4.3` 


## Attribute Details

### AbsoluteExpirationTime

Absolute expiration time of the session. Not empty if the session is created by a service appllication. `Required` `Filter(ge;le)` `ORD`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Applications

A comma separated list of client applications that share this session. `Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CurrentRequestsCount

The requests count in the time of the request. `Required` `Filter(ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Device

The name of the user's device. `Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### DownloadMB

The downloaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### LastRequestTime

The last request time. `Required` `Filter(ge;le)` `ORD`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### SessionId

The id of the session. `Required` `Filter(eq)` `Introduced in version 26.1.4.3`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### StartTime

The login time of the session. `Required` `Filter(ge;le)` `ORD`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TotalRequestsCount

The total request count at the time of the request. `Required` `Filter(ge;le)` `ORD`

Type: **int64**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### UploadMB

The uploaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### UserLogin

The user login name. `Required` `Introduced in version 26.1.4.3`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_CurrentSessions

Domain API Entity Type: 
Systems_Monitoring_CurrentSessionsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_CurrentSessions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_CurrentSessions?$top=10>

