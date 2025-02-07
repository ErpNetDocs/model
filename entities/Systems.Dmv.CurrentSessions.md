---
uid: Systems.Dmv.CurrentSessions
---
# Systems.Dmv.CurrentSessions View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Sessions dynamic management view. Entity: Dmv_Current_Sessions (Introduced in version 23.1.1.52)
## Renamed
**New name:** [Systems.Monitoring.CurrentSessions](Systems.Monitoring.CurrentSessions.md)  



## Default Visualization
Default Display Text Format:  
_{User}: {Device}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.CurrentSessions](Systems.Dmv.CurrentSessions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AbsoluteExpirationTime](Systems.Dmv.CurrentSessions.md#absoluteexpirationtime) | datetime | Absolute expiration time of the session. Not empty if the session is created by a service appllication. `Required` `Filter(ge;le)` `ORD` 
| [Applications](Systems.Dmv.CurrentSessions.md#applications) | string (64) | A comma separated list of client applications that share this session. `Required` `Filter(eq;like)` `ORD` 
| [CurrentRequestsCount](Systems.Dmv.CurrentSessions.md#currentrequestscount) | int32 | The requests count in the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [Device](Systems.Dmv.CurrentSessions.md#device) | string (64) | The name of the user's device. `Required` `Filter(eq;like)` `ORD` 
| [DownloadMB](Systems.Dmv.CurrentSessions.md#downloadmb) | decimal (12, 3) | The downloaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [LastRequestTime](Systems.Dmv.CurrentSessions.md#lastrequesttime) | datetime | The last request time. `Required` `Filter(ge;le)` `ORD` 
| [StartTime](Systems.Dmv.CurrentSessions.md#starttime) | datetime | The login time of the session. `Required` `Filter(ge;le)` `ORD` 
| [TotalRequestsCount](Systems.Dmv.CurrentSessions.md#totalrequestscount) | int64 | The total request count at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [UploadMB](Systems.Dmv.CurrentSessions.md#uploadmb) | decimal (12, 3) | The uploaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [User](Systems.Dmv.CurrentSessions.md#user) | string (64) | The login name of the session's user. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### AbsoluteExpirationTime

Absolute expiration time of the session. Not empty if the session is created by a service appllication. `Required` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Applications

A comma separated list of client applications that share this session. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### CurrentRequestsCount

The requests count in the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Device

The name of the user's device. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### DownloadMB

The downloaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### LastRequestTime

The last request time. `Required` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### StartTime

The login time of the session. `Required` `Filter(ge;le)` `ORD`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### TotalRequestsCount

The total request count at the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **int64**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### UploadMB

The uploaded megabytes at the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### User

The login name of the session's user. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_CurrentSessions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_CurrentSessions?$top=10>

