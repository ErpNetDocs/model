---
uid: Systems.Monitoring.ExecStats
---
# Systems.Monitoring.ExecStats (View)


Execution statistics dynamic management view

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ExecStats  
Introduced In Version: 23.1.0.19  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.ExecStats  
New name: Systems.Monitoring.ExecStats  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Application}: {Database}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ExecStats](Systems.Monitoring.ExecStats.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Application](Systems.Monitoring.ExecStats.md#application) | string (64) | The name of the application that executes the operation 
| [AvgTimeMs](Systems.Monitoring.ExecStats.md#avgtimems) | double | Average time of operation execution 
| [Count](Systems.Monitoring.ExecStats.md#count) | int32 | The number of times the operation is executed since last statistics reset. 
| [Database](Systems.Monitoring.ExecStats.md#database) | string (64) | The database in which the operation is executed 
| [IsLongPolling](Systems.Monitoring.ExecStats.md#islongpolling) | boolean | True if the operation is long polling. 
| [Kind](Systems.Monitoring.ExecStats.md#kind) | string (64) | The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc. 
| [MaxTimeMs](Systems.Monitoring.ExecStats.md#maxtimems) | double | The maximum time of one operation execution 
| [Operation](Systems.Monitoring.ExecStats.md#operation) | string (128) | The operation name 
| [StatisticsSince](Systems.Monitoring.ExecStats.md#statisticssince) | datetime | The date and time since when the statistics are collected 
| [TotalTimeMs](Systems.Monitoring.ExecStats.md#totaltimems) | double | Total time spent for the operation 


## Attribute Details

### Application

The name of the application that executes the operation

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### AvgTimeMs

Average time of operation execution

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Count

The number of times the operation is executed since last statistics reset.

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Database

The database in which the operation is executed

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### IsLongPolling

True if the operation is long polling.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Kind

The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### MaxTimeMs

The maximum time of one operation execution

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Operation

The operation name

Type: **string (128)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalTimeMs

Total time spent for the operation

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### ResetStats

Reset performace statistics  
Return Type: **void**  
Declaring Type: **[ExecStats](Systems.Monitoring.ExecStats.md)**  
Domain API Request: **POST**  

## API

Domain API Entity Set: 
Systems_Monitoring_ExecStats

Domain API Entity Type: 
Systems_Monitoring_ExecStatsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ExecStats?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ExecStats?$top=10>

