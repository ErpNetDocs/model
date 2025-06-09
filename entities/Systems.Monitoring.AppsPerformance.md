---
uid: Systems.Monitoring.AppsPerformance
---
# Systems.Monitoring.AppsPerformance View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Applications performance statistics dynamic management view. Entity: Dmv_Apps_Performance (Introduced in version 25.1.3.47)

## Default Visualization
Default Display Text Format:  
_{Application}: {Requests}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AppsPerformance](Systems.Monitoring.AppsPerformance.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Application](Systems.Monitoring.AppsPerformance.md#application) | string (64) | The name of the application that executes the operation. `Required` `Filter(eq;ge;le)` `ORD` 
| [BusyTimeHoursPerDay](Systems.Monitoring.AppsPerformance.md#busytimehoursperday) | double | Busy time in percentage per day. `Required` `Filter(ge;le)` `ORD` 
| [BusyTimePercentage](Systems.Monitoring.AppsPerformance.md#busytimepercentage) | double | Busy time in percentage. `Required` `Filter(ge;le)` `ORD` 
| [Requests](Systems.Monitoring.AppsPerformance.md#requests) | int32 | The total number of requests the application has made to the server. `Required` `Filter(eq;like)` `ORD` 
| [StatisticsSince](Systems.Monitoring.AppsPerformance.md#statisticssince) | datetime | The date and time since when the statistics are collected. `Required` `Filter(ge;le)` `ORD` `Introduced in version 25.1.3.60` 


## Attribute Details

### Application

The name of the application that executes the operation. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### BusyTimeHoursPerDay

Busy time in percentage per day. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### BusyTimePercentage

Busy time in percentage. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Requests

The total number of requests the application has made to the server. `Required` `Filter(eq;like)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected. `Required` `Filter(ge;le)` `ORD` `Introduced in version 25.1.3.60`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_AppsPerformance?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_AppsPerformance?$top=10>

