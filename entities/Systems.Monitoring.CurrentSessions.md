---
uid: Systems.Monitoring.CurrentSessions
---
# Systems.Monitoring.CurrentSessions View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Sessions dynamic management view. Entity: Dmv_Current_Sessions (Introduced in version 23.1.1.52)

## Renames

Old name: **Systems.Dmv.CurrentSessions**  
New name: **Systems.Monitoring.CurrentSessions**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{SessionId}: {UserLogin}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

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

### SessionId

The id of the session. `Required` `Filter(eq)` `Introduced in version 26.1.4.3`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
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

### UserLogin

The user login name. `Required` `Introduced in version 26.1.4.3`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_CurrentSessions

Domain API Entity Type: 
Systems_Monitoring_CurrentSessionsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_CurrentSessions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_CurrentSessions?$top=10>

