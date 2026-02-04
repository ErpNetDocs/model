---
uid: Systems.Monitoring.AppsPerformance
---
# Systems.Monitoring.AppsPerformance (View)


Applications performance statistics dynamic management view

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.AppsPerformance  
Introduced In Version: 25.1.3.47  
API access:  ReadWrite  

## Visualization
Display Format: {Application}: {Requests}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AppsPerformance](Systems.Monitoring.AppsPerformance.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Application](Systems.Monitoring.AppsPerformance.md#application) | string (64) | The name of the application that executes the operation 
| [BusyTimeHoursPerDay](Systems.Monitoring.AppsPerformance.md#busytimehoursperday) | double | Busy time in percentage per day 
| [BusyTimePercentage](Systems.Monitoring.AppsPerformance.md#busytimepercentage) | double | Busy time in percentage 
| [Requests](Systems.Monitoring.AppsPerformance.md#requests) | double | The total number of requests the application has made to the server 
| [StatisticsSince](Systems.Monitoring.AppsPerformance.md#statisticssince) | datetime | The date and time since when the statistics are collected. `Required` `Filter(ge;le)` `ORD` `Introduced in version 25.1.3.60` 


## Attribute Details

### Application

The name of the application that executes the operation

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### BusyTimeHoursPerDay

Busy time in percentage per day

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### BusyTimePercentage

Busy time in percentage

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Requests

The total number of requests the application has made to the server

Type: **double**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected. `Required` `Filter(ge;le)` `ORD` `Introduced in version 25.1.3.60`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_AppsPerformance

Domain API Entity Type: 
Systems_Monitoring_AppsPerformanceEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_AppsPerformance?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_AppsPerformance?$top=10>

