---
uid: Systems.Monitoring.DbResourceUtilization
---
# Systems.Monitoring.DbResourceUtilization (View)


Provides aggregated metrics for database query execution within a given time interval. The data reflects system workload, including CPU usage, waiting time, memory consumption, and I/O activity. Useful for performance monitoring, workload analysis, and automated diagnostics.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.DbResourceUtilization  
Introduced In Version: 26.2.2.11  
API access:  ReadWrite  

## Visualization
Display Format: {IntervalId}: {IntervalStartUtc}  
Search Members:   
Category:  Views  
Show in UI:  HiddenByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.DbResourceUtilization](Systems.Monitoring.DbResourceUtilization.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvgCpuCores](Systems.Monitoring.DbResourceUtilization.md#avgcpucores) | double | Average CPU execution load, expressed in CPU cores (relative to 1 core). `Required` |
| [AvgMemoryPerQueryMB](Systems.Monitoring.DbResourceUtilization.md#avgmemoryperquerymb) | double | Average memory (MB) used per query execution. `Required` |
| [AvgTotalCores](Systems.Monitoring.DbResourceUtilization.md#avgtotalcores) | double | Average total load, expressed in CPU cores (relative to 1 core). `Required` |
| [AvgTotalQueryMemoryMB](Systems.Monitoring.DbResourceUtilization.md#avgtotalquerymemorymb) | double | Average total memory (MB) consumed by all concurrent query executions. `Required` |
| [AvgWaitingCores](Systems.Monitoring.DbResourceUtilization.md#avgwaitingcores) | double | Average waiting load, expressed in CPU cores (relative to 1 core). `Required` |
| [ExecutionCount](Systems.Monitoring.DbResourceUtilization.md#executioncount) | int64 | Total number of executed queries during the interval. `Required` |
| [ExecutionDurationMs](Systems.Monitoring.DbResourceUtilization.md#executiondurationms) | double | Total duration (ms) of all completed query executions in the interval.`Required` |
| [ExecutionsPerSecond](Systems.Monitoring.DbResourceUtilization.md#executionspersecond) | double | Average number of queries executed per second. `Required` |
| [IntervalCompletionRatio](Systems.Monitoring.DbResourceUtilization.md#intervalcompletionratio) | double | Ratio (0–1) indicating how much of the interval has elapsed. Values &lt; 1 mean the interval is still active and data is not final. `Required` |
| [IntervalEndUtc](Systems.Monitoring.DbResourceUtilization.md#intervalendutc) | datetime | End timestamp of the interval in UTC.`Required` `Filter(ge;le)` |
| [IntervalId](Systems.Monitoring.DbResourceUtilization.md#intervalid) | int64 | Unique identifier of the runtime interval.`Required` `Filter(eq)` |
| [IntervalIsCompleted](Systems.Monitoring.DbResourceUtilization.md#intervaliscompleted) | boolean | Indicates whether this is completed or still active interval.`Required` `Filter(eq)` |
| [IntervalStartUtc](Systems.Monitoring.DbResourceUtilization.md#intervalstartutc) | datetime | Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)` |
| [LogicalReads](Systems.Monitoring.DbResourceUtilization.md#logicalreads) | int64 | Total logical reads executed during the interval.`Required` |
| [LogicalWrites](Systems.Monitoring.DbResourceUtilization.md#logicalwrites) | int64 |  Total logical writes executed during the interval.`Required` |
| [PhysicalReadsCount](Systems.Monitoring.DbResourceUtilization.md#physicalreadscount) | int64 | Total physical reads executed during the interval.`Required` |
| [PhysicalReadsMB](Systems.Monitoring.DbResourceUtilization.md#physicalreadsmb) | double | Total disk read volume (MB) during the interval.`Required` |
| [PhysicalReadsMBps](Systems.Monitoring.DbResourceUtilization.md#physicalreadsmbps) | double | Average disk read throughput (MB/s) during the interval.`Required` |
| [WaitCpuMs](Systems.Monitoring.DbResourceUtilization.md#waitcpums) | int64 | Total wait time (ms) due to CPU resource contention. `Required` |
| [WaitIoMs](Systems.Monitoring.DbResourceUtilization.md#waitioms) | int64 | Total wait time (ms) related to I/O operations. `Required` |
| [WaitLockMs](Systems.Monitoring.DbResourceUtilization.md#waitlockms) | int64 | Total wait time (ms) caused by locks or blocking. `Required` |
| [WaitMemoryMs](Systems.Monitoring.DbResourceUtilization.md#waitmemoryms) | int64 | Total wait time (ms) due to memory resource contention. `Required` |
| [WaitNetworkMs](Systems.Monitoring.DbResourceUtilization.md#waitnetworkms) | int64 | Total wait time (ms) caused by network transfer-related waits. `Required` |
| [WaitOtherMs](Systems.Monitoring.DbResourceUtilization.md#waitotherms) | int64 | Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network. `Required` |


## Attribute Details

### AvgCpuCores

Average CPU execution load, expressed in CPU cores (relative to 1 core). `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgMemoryPerQueryMB

Average memory (MB) used per query execution. `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalCores

Average total load, expressed in CPU cores (relative to 1 core). `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalQueryMemoryMB

Average total memory (MB) consumed by all concurrent query executions. `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgWaitingCores

Average waiting load, expressed in CPU cores (relative to 1 core). `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionCount

Total number of executed queries during the interval. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionDurationMs

Total duration (ms) of all completed query executions in the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionsPerSecond

Average number of queries executed per second. `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalCompletionRatio

Ratio (0–1) indicating how much of the interval has elapsed. Values &lt; 1 mean the interval is still active and data is not final. `Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalEndUtc

End timestamp of the interval in UTC.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalId

Unique identifier of the runtime interval.`Required` `Filter(eq)`

Type: **int64**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalIsCompleted

Indicates whether this is completed or still active interval.`Required` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalStartUtc

Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LogicalReads

Total logical reads executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LogicalWrites

Total logical writes executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsCount

Total physical reads executed during the interval.`Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsMB

Total disk read volume (MB) during the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsMBps

Average disk read throughput (MB/s) during the interval.`Required`

Type: **double**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitCpuMs

Total wait time (ms) due to CPU resource contention. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitIoMs

Total wait time (ms) related to I/O operations. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitLockMs

Total wait time (ms) caused by locks or blocking. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitMemoryMs

Total wait time (ms) due to memory resource contention. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitNetworkMs

Total wait time (ms) caused by network transfer-related waits. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitOtherMs

Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network. `Required`

Type: **int64**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_DbResourceUtilization

Domain API Entity Type: 
Systems_Monitoring_DbResourceUtilizationEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_DbResourceUtilization?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_DbResourceUtilization?$top=10>

