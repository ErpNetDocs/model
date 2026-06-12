---
uid: Dmv.ExecStats
---
# Dmv.ExecStats View

**Namespace:** [Dmv](Dmv.md)  

## Default Visualization
Default Display Text Format:  
_{Application}: {Database}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Dmv.ExecStats](Dmv.ExecStats.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Application](Dmv.ExecStats.md#application) | string (64) | The name of the application that executes the operation. `Required` `Filter(eq;like)` `ORD` 
| [AvgTimeMs](Dmv.ExecStats.md#avgtimems) | double | Average time of operation execution. `Required` `Filter(ge;le)` `ORD` 
| [Count](Dmv.ExecStats.md#count) | int32 | The number of times the operation is executed since last statistics reset. `Required` `Filter(ge;le)` `ORD` 
| [Database](Dmv.ExecStats.md#database) | string (64) | The database in which the operation is executed. `Required` `Filter(eq;like)` `ORD` 
| [IsLongPolling](Dmv.ExecStats.md#islongpolling) | boolean | True if the operation is long polling. `Required` `Filter(eq)` 
| [Kind](Dmv.ExecStats.md#kind) | string (64) | The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc. `Required` `Filter(eq;like)` `ORD` 
| [MaxTimeMs](Dmv.ExecStats.md#maxtimems) | double | The maximum time of one operation execution. `Required` `Filter(ge;le)` `ORD` 
| [Operation](Dmv.ExecStats.md#operation) | string (128) | The operation name. `Required` `Filter(like)` 
| [StatisticsSince](Dmv.ExecStats.md#statisticssince) | datetime | The date and time since when the statistics are collected. `Required` `Filter(ge;le)` 
| [TotalTimeMs](Dmv.ExecStats.md#totaltimems) | double | Total time spent for the operation. `Required` `Filter(ge;le)` `ORD` 


## Attribute Details

### Application

The name of the application that executes the operation. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  

### AvgTimeMs

Average time of operation execution. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  

### Count

The number of times the operation is executed since last statistics reset. `Required` `Filter(ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  

### Database

The database in which the operation is executed. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  

### IsLongPolling

True if the operation is long polling. `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### Kind

The operation kind. Various operation kinds exist, e.g. Db, Long Procs etc. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  

### MaxTimeMs

The maximum time of one operation execution. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  

### Operation

The operation name. `Required` `Filter(like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  

### StatisticsSince

The date and time since when the statistics are collected. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### TotalTimeMs

Total time spent for the operation. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Dmv_ExecStats?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Dmv_ExecStats?$top=10>

