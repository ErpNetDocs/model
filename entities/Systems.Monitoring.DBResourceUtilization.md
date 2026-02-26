---
uid: Systems.Monitoring.DBResourceUtilization
---
# Systems.Monitoring.DBResourceUtilization (View)


Returns diagnostic execution metrics for database queries within a specific Query Store interval. Values are aggregated, normalized, and partially recalculated from Query Store views (query_store_runtime_stats_interval, query_store_runtime_stats, query_store_wait_stats). Useful for performance monitoring, workload analysis, and automated diagnostics.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.DBResourceUtilization  
Introduced In Version: 26.2.1.65  
API access:  ReadOnly  

## Visualization
Display Format: {RuntimeIntervalId}: {TimeSlotBeginUtc}  
Search Members:   
Category:  Views  
Show in UI:  HiddenByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.DBResourceUtilization](Systems.Monitoring.DBResourceUtilization.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvgCoresCPU](Systems.Monitoring.DBResourceUtilization.md#avgcorescpu) | double | Normalized average CPU utilization by query executions in CPU-core units.`Required` 
| [AvgCoresTotal](Systems.Monitoring.DBResourceUtilization.md#avgcorestotal) | double | Normalized average query execution duration in CPU-core units.`Required` 
| [AvgCoresWaiting](Systems.Monitoring.DBResourceUtilization.md#avgcoreswaiting) | double | Normalized average wait time for CPU/memory/IO/locks  in CPU-core units.`Required` 
| [AvgMemoryperQueryMB](Systems.Monitoring.DBResourceUtilization.md#avgmemoryperquerymb) | double | Average memory used per executed query.`Required` 
| [AvgQueryMemoryUsageMB](Systems.Monitoring.DBResourceUtilization.md#avgquerymemoryusagemb) | double | Average SQL Server memory usage attributable to query execution (query memory grant usage).`Required` 
| [DiskReadMB](Systems.Monitoring.DBResourceUtilization.md#diskreadmb) | double | Total disk-read volume (MB) during the interval.`Required` 
| [DiskReadThroughputMBps](Systems.Monitoring.DBResourceUtilization.md#diskreadthroughputmbps) | double | Average disk-read throughput (MB/s) during the interval.`Required` 
| [ExecutionCount](Systems.Monitoring.DBResourceUtilization.md#executioncount) | int64 | Total number of query executions during the interval.`Required` 
| [ExecutionsperSecond](Systems.Monitoring.DBResourceUtilization.md#executionspersecond) | double | Average executions per second within the interval.`Required` 
| [IntervalCompletionRatio](Systems.Monitoring.DBResourceUtilization.md#intervalcompletionratio) | double | Ratio (0–1) indicating how much of the interval has elapsed. Values < 1 mean the interval is still active and data is not final.`Required` `Filter(eq)` 
| [RuntimeIntervalId](Systems.Monitoring.DBResourceUtilization.md#runtimeintervalid) | int64 | Identifier of the Query Store runtime interval (runtime_stats_interval_id).`Required` `Filter(eq;ge;le)` `ORD` 
| [TimeSlotBeginUtc](Systems.Monitoring.DBResourceUtilization.md#timeslotbeginutc) | datetime | Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)` `ORD` 
| [TimeSlotEndUtc](Systems.Monitoring.DBResourceUtilization.md#timeslotendutc) | datetime | End timestamp of the interval in UTC.`Required` `Filter(ge;le)` 
| [TotalDurationms](Systems.Monitoring.DBResourceUtilization.md#totaldurationms) | double | Total duration (ms) of all completed executions in the interval.`Required` 
| [TotalLogicalReads](Systems.Monitoring.DBResourceUtilization.md#totallogicalreads) | int64 | Total logical reads executed during the interval.`Required` 
| [TotalLogicalWrites](Systems.Monitoring.DBResourceUtilization.md#totallogicalwrites) | int64 | Total logical writes executed during the interval.`Required` 
| [TotalPhysicalReads](Systems.Monitoring.DBResourceUtilization.md#totalphysicalreads) | int64 | Total physical reads executed during the interval.`Required` 
| [WaitCPUms](Systems.Monitoring.DBResourceUtilization.md#waitcpums) | int64 | Total wait time due to CPU resource contention.`Required` 
| [WaitIOms](Systems.Monitoring.DBResourceUtilization.md#waitioms) | int64 | Total wait time related to IO operations.`Required` 
| [WaitLockms](Systems.Monitoring.DBResourceUtilization.md#waitlockms) | int64 | Total wait time caused by locks or blocking`Required` 
| [WaitMemoryms](Systems.Monitoring.DBResourceUtilization.md#waitmemoryms) | int64 | Total wait time due to memory resource contention.`Required` 
| [WaitNetworkms](Systems.Monitoring.DBResourceUtilization.md#waitnetworkms) | int64 | Total wait time caused by network transfer-related waits.`Required` 
| [WaitOtherms](Systems.Monitoring.DBResourceUtilization.md#waitotherms) | int64 | Total wait time for all remaining wait categories.`Required` 


## Attribute Details

### AvgCoresCPU

Normalized average CPU utilization by query executions in CPU-core units.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgCoresTotal

Normalized average query execution duration in CPU-core units.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgCoresWaiting

Normalized average wait time for CPU/memory/IO/locks  in CPU-core units.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgMemoryperQueryMB

Average memory used per executed query.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgQueryMemoryUsageMB

Average SQL Server memory usage attributable to query execution (query memory grant usage).`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DiskReadMB

Total disk-read volume (MB) during the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DiskReadThroughputMBps

Average disk-read throughput (MB/s) during the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionCount

Total number of query executions during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionsperSecond

Average executions per second within the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalCompletionRatio

Ratio (0–1) indicating how much of the interval has elapsed. Values < 1 mean the interval is still active and data is not final.`Required` `Filter(eq)`

Type: **double**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RuntimeIntervalId

Identifier of the Query Store runtime interval (runtime_stats_interval_id).`Required` `Filter(eq;ge;le)` `ORD`

Type: **int64**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TimeSlotBeginUtc

Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)` `ORD`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TimeSlotEndUtc

End timestamp of the interval in UTC.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalDurationms

Total duration (ms) of all completed executions in the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalLogicalReads

Total logical reads executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalLogicalWrites

Total logical writes executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalPhysicalReads

Total physical reads executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitCPUms

Total wait time due to CPU resource contention.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitIOms

Total wait time related to IO operations.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitLockms

Total wait time caused by locks or blocking`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitMemoryms

Total wait time due to memory resource contention.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitNetworkms

Total wait time caused by network transfer-related waits.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitOtherms

Total wait time for all remaining wait categories.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_DBResourceUtilization

Domain API Entity Type: 
Systems_Monitoring_DBResourceUtilizationEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_DBResourceUtilization?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_DBResourceUtilization?$top=10>

