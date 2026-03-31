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
| [AvgCpuCores](Systems.Monitoring.DBResourceUtilization.md#avgcpucores) | double __nullable__ | Average CPU execution load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3` |
| [AvgMemoryPerQueryMB](Systems.Monitoring.DBResourceUtilization.md#avgmemoryperquerymb) | double __nullable__ | Average memory (MB) used per query execution. `Introduced in version 26.2.2.3` |
| [AvgTotalCores](Systems.Monitoring.DBResourceUtilization.md#avgtotalcores) | double __nullable__ | Average total load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3` |
| [AvgTotalQueryMemoryMB](Systems.Monitoring.DBResourceUtilization.md#avgtotalquerymemorymb) | double __nullable__ | Average total memory (MB) consumed by all concurrent query executions. `Introduced in version 26.2.2.3` |
| [AvgWaitingCores](Systems.Monitoring.DBResourceUtilization.md#avgwaitingcores) | double __nullable__ | Average waiting load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3` |
| [DiskReadMBps](Systems.Monitoring.DBResourceUtilization.md#diskreadmbps) | double __nullable__ | Average disk read throughput (MB/s) during the interval. `Introduced in version 26.2.2.3` |
| [DiskReadTotalMB](Systems.Monitoring.DBResourceUtilization.md#diskreadtotalmb) | double __nullable__ | Total disk read volume (MB) during the interval. `Introduced in version 26.2.2.3` |
| [ExecutionCount](Systems.Monitoring.DBResourceUtilization.md#executioncount) | int64 __nullable__ | Total number of query executions during the interval. |
| [ExecutionsPerSecond](Systems.Monitoring.DBResourceUtilization.md#executionspersecond) | double __nullable__ | Average number of queries executed per second. `Introduced in version 26.2.2.3` |
| [IntervalCompletionRatio](Systems.Monitoring.DBResourceUtilization.md#intervalcompletionratio) | double __nullable__ | Ratio (0–1) indicating how much of the interval has elapsed. Values < 1 mean the interval is still active and data is not final. |
| [IsIntervalComplete](Systems.Monitoring.DBResourceUtilization.md#isintervalcomplete) | boolean __nullable__ | Indicates whether this is completed or still active interval. `Filter(eq)` `Introduced in version 26.2.2.3` |
| [RuntimeIntervalId](Systems.Monitoring.DBResourceUtilization.md#runtimeintervalid) | int64 __nullable__ | Identifier of the Query Store runtime interval (runtime_stats_interval_id).`Filter(eq;ge;le)` `ORD` |
| [TimeSlotBeginUtc](Systems.Monitoring.DBResourceUtilization.md#timeslotbeginutc) | datetime | Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)` `ORD` |
| [TimeSlotEndUtc](Systems.Monitoring.DBResourceUtilization.md#timeslotendutc) | datetime | End timestamp of the interval in UTC.`Required` `Filter(ge;le)` |
| [TotalDurationMs](Systems.Monitoring.DBResourceUtilization.md#totaldurationms) | double __nullable__ | Total duration (ms) of all completed query executions in the interval. `Introduced in version 26.2.2.3` |
| [TotalLogicalReads](Systems.Monitoring.DBResourceUtilization.md#totallogicalreads) | int64 __nullable__ | Total logical reads executed during the interval. |
| [TotalLogicalWrites](Systems.Monitoring.DBResourceUtilization.md#totallogicalwrites) | int64 __nullable__ | Total logical writes executed during the interval. |
| [TotalPhysicalReads](Systems.Monitoring.DBResourceUtilization.md#totalphysicalreads) | int64 __nullable__ | Total physical reads executed during the interval. |
| [WaitCpuMs](Systems.Monitoring.DBResourceUtilization.md#waitcpums) | int64 __nullable__ | Total wait time (ms) due to CPU resource contention. `Introduced in version 26.2.2.3` |
| [WaitIoMs](Systems.Monitoring.DBResourceUtilization.md#waitioms) | int64 __nullable__ | Total wait time (ms) related to I/O operations. `Introduced in version 26.2.2.3` |
| [WaitLockMs](Systems.Monitoring.DBResourceUtilization.md#waitlockms) | int64 __nullable__ | Total wait time (ms) caused by locks or blocking. `Introduced in version 26.2.2.3` |
| [WaitMemoryMs](Systems.Monitoring.DBResourceUtilization.md#waitmemoryms) | int64 __nullable__ | Total wait time (ms) due to memory resource contention. `Introduced in version 26.2.2.3` |
| [WaitNetworkMs](Systems.Monitoring.DBResourceUtilization.md#waitnetworkms) | int64 __nullable__ | Total wait time (ms) caused by network transfer-related waits. `Introduced in version 26.2.2.3` |
| [WaitOtherMs](Systems.Monitoring.DBResourceUtilization.md#waitotherms) | int64 __nullable__ | Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network. `Introduced in version 26.2.2.3` |


## Attribute Details

### AvgCpuCores

Average CPU execution load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgMemoryPerQueryMB

Average memory (MB) used per query execution. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalCores

Average total load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalQueryMemoryMB

Average total memory (MB) consumed by all concurrent query executions. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgWaitingCores

Average waiting load, expressed in CPU cores (relative to 1 core). `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DiskReadMBps

Average disk read throughput (MB/s) during the interval. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DiskReadTotalMB

Total disk read volume (MB) during the interval. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionCount

Total number of query executions during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionsPerSecond

Average number of queries executed per second. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalCompletionRatio

Ratio (0–1) indicating how much of the interval has elapsed. Values < 1 mean the interval is still active and data is not final.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsIntervalComplete

Indicates whether this is completed or still active interval. `Filter(eq)` `Introduced in version 26.2.2.3`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RuntimeIntervalId

Identifier of the Query Store runtime interval (runtime_stats_interval_id).`Filter(eq;ge;le)` `ORD`

Type: **int64 __nullable__**  
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

### TotalDurationMs

Total duration (ms) of all completed query executions in the interval. `Introduced in version 26.2.2.3`

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalLogicalReads

Total logical reads executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalLogicalWrites

Total logical writes executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalPhysicalReads

Total physical reads executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitCpuMs

Total wait time (ms) due to CPU resource contention. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitIoMs

Total wait time (ms) related to I/O operations. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitLockMs

Total wait time (ms) caused by locks or blocking. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitMemoryMs

Total wait time (ms) due to memory resource contention. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitNetworkMs

Total wait time (ms) caused by network transfer-related waits. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitOtherMs

Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network. `Introduced in version 26.2.2.3`

Type: **int64 __nullable__**  
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

