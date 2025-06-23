---
uid: Systems.Monitoring.ExecStats
---
# Systems.Monitoring.ExecStats View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Execution statistics dynamic management view. Entity: Dmv_Exec_Stats (Introduced in version 23.1.0.19)

## Renames

Old name: **Systems.Dmv.ExecStats**  
New name: **Systems.Monitoring.ExecStats**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Application}: {Database}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ExecStats](Systems.Monitoring.ExecStats.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Application](Systems.Monitoring.ExecStats.md#application) | string (64) | The name of the application that executes the operation. `Required` `Filter(eq;like)` `ORD` 
| [AvgTimeMs](Systems.Monitoring.ExecStats.md#avgtimems) | double | Average time of operation execution. `Required` `Filter(ge;le)` `ORD` 
| [Count](Systems.Monitoring.ExecStats.md#count) | int32 | The number of times the operation is executed since last statistics reset. `Required` `Filter(ge;le)` `ORD` 
| [Database](Systems.Monitoring.ExecStats.md#database) | string (64) | The database in which the operation is executed. `Required` `Filter(eq;like)` `ORD` 
| [IsLongPolling](Systems.Monitoring.ExecStats.md#islongpolling) | boolean | True if the operation is long polling. `Required` `Filter(eq)` 
| [Kind](Systems.Monitoring.ExecStats.md#kind) | string (64) | The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc. `Required` `Filter(eq;like)` `ORD` 
| [MaxTimeMs](Systems.Monitoring.ExecStats.md#maxtimems) | double | The maximum time of one operation execution. `Required` `Filter(ge;le)` `ORD` 
| [Operation](Systems.Monitoring.ExecStats.md#operation) | string (128) | The operation name. `Required` `Filter(like)` 
| [StatisticsSince](Systems.Monitoring.ExecStats.md#statisticssince) | datetime | The date and time since when the statistics are collected. `Required` `Filter(ge;le)` 
| [TotalTimeMs](Systems.Monitoring.ExecStats.md#totaltimems) | double | Total time spent for the operation. `Required` `Filter(ge;le)` `ORD` 


## Attribute Details

### Application

The name of the application that executes the operation. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### AvgTimeMs

Average time of operation execution. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Count

The number of times the operation is executed since last statistics reset. `Required` `Filter(ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Database

The database in which the operation is executed. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### IsLongPolling

True if the operation is long polling. `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Kind

The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### MaxTimeMs

The maximum time of one operation execution. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Operation

The operation name. `Required` `Filter(like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalTimeMs

Total time spent for the operation. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_ExecStats?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ExecStats?$top=10>

