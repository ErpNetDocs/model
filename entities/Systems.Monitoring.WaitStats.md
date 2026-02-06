---
uid: Systems.Monitoring.WaitStats
---
# Systems.Monitoring.WaitStats (View)


Wait statistics dynamic management view

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.WaitStats  
Introduced In Version: 25.1.0.38  
API access:  ReadWrite  

## Visualization
Display Format: {Database}: {WaitCategory}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.WaitStats](Systems.Monitoring.WaitStats.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Database](Systems.Monitoring.WaitStats.md#database) | string (64) | The database in which the wait operation is located 
| [MaxHoldLockTimeMs](Systems.Monitoring.WaitStats.md#maxholdlocktimems) | double | Maximum time a lock was held, measured in milliseconds. 
| [MaxWaitTimeMs](Systems.Monitoring.WaitStats.md#maxwaittimems) | double | Maximum wait time for acquiring a lock, measured in milliseconds. 
| [StatisticsSince](Systems.Monitoring.WaitStats.md#statisticssince) | datetime | The date and time since when the statistics are collected 
| [TotalFailedAttempts](Systems.Monitoring.WaitStats.md#totalfailedattempts) | double | Indicates the total number of unsuccessful attempts to acquire locks. 
| [TotalFailWaitTimeMs](Systems.Monitoring.WaitStats.md#totalfailwaittimems) | double | Общо време на изчакване за неуспешни заключвания, измерено в милисекунди. 
| [TotalHoldLockTimeMs](Systems.Monitoring.WaitStats.md#totalholdlocktimems) | double | Indicates the total duration locks are held, measured in milliseconds. 
| [TotalLocks](Systems.Monitoring.WaitStats.md#totallocks) | double | The total number of locks. 
| [TotalSuccessWaitTimeMs](Systems.Monitoring.WaitStats.md#totalsuccesswaittimems) | double | Indicates the cumulative time spent waiting for successful lock acquisitions, measured in milliseconds. 
| [TotalWaitLocks](Systems.Monitoring.WaitStats.md#totalwaitlocks) | double | Indicates the total number of locks that have been acquired after waiting. 
| [WaitCategory](Systems.Monitoring.WaitStats.md#waitcategory) | string (128) | The category of the wait operation. 


## Attribute Details

### Database

The database in which the wait operation is located

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### MaxHoldLockTimeMs

Maximum time a lock was held, measured in milliseconds.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MaxWaitTimeMs

Maximum wait time for acquiring a lock, measured in milliseconds.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalFailedAttempts

Indicates the total number of unsuccessful attempts to acquire locks.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalFailWaitTimeMs

Общо време на изчакване за неуспешни заключвания, измерено в милисекунди.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalHoldLockTimeMs

Indicates the total duration locks are held, measured in milliseconds.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalLocks

The total number of locks.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalSuccessWaitTimeMs

Indicates the cumulative time spent waiting for successful lock acquisitions, measured in milliseconds.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalWaitLocks

Indicates the total number of locks that have been acquired after waiting.

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitCategory

The category of the wait operation.

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### ResetStats

Reset wait statistics  
Return Type: **void**  
Declaring Type: **[WaitStats](Systems.Monitoring.WaitStats.md)**  
Domain API Request: **POST**  

## API

Domain API Entity Set: 
Systems_Monitoring_WaitStats

Domain API Entity Type: 
Systems_Monitoring_WaitStatsEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_WaitStats?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_WaitStats?$top=10>

