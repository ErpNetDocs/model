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
| [AvgCpuCores](Systems.Monitoring.DbResourceUtilization.md#avgcpucores) | double __nullable__ | Average CPU execution load, expressed in CPU cores (relative to 1 core). |
| [AvgMemoryPerQueryMB](Systems.Monitoring.DbResourceUtilization.md#avgmemoryperquerymb) | double __nullable__ | Average memory (MB) used per query execution. |
| [AvgTotalCores](Systems.Monitoring.DbResourceUtilization.md#avgtotalcores) | double __nullable__ | Average total load, expressed in CPU cores (relative to 1 core). |
| [AvgTotalQueryMemoryMB](Systems.Monitoring.DbResourceUtilization.md#avgtotalquerymemorymb) | double __nullable__ | Average total memory (MB) consumed by all concurrent query executions. |
| [AvgWaitingCores](Systems.Monitoring.DbResourceUtilization.md#avgwaitingcores) | double __nullable__ | Average waiting load, expressed in CPU cores (relative to 1 core). |
| [ExecutionCount](Systems.Monitoring.DbResourceUtilization.md#executioncount) | int64 __nullable__ | Total number of executed queries during the interval. |
| [ExecutionDurationMs](Systems.Monitoring.DbResourceUtilization.md#executiondurationms) | double __nullable__ | Total duration (ms) of all completed query executions in the interval. |
| [ExecutionsPerSecond](Systems.Monitoring.DbResourceUtilization.md#executionspersecond) | double __nullable__ | Average number of queries executed per second. |
| [IntervalCompletionRatio](Systems.Monitoring.DbResourceUtilization.md#intervalcompletionratio) | double __nullable__ | Ratio (0–1) indicating how much of the interval has elapsed. Values &lt; 1 mean the interval is still active and data is not final. |
| [IntervalEndUtc](Systems.Monitoring.DbResourceUtilization.md#intervalendutc) | datetime | End timestamp of the interval in UTC.`Required` `Filter(ge;le)` |
| [IntervalId](Systems.Monitoring.DbResourceUtilization.md#intervalid) | int64 __nullable__ | Unique identifier of the runtime interval.`Filter(eq)` |
| [IntervalIsCompleted](Systems.Monitoring.DbResourceUtilization.md#intervaliscompleted) | boolean __nullable__ | Indicates whether this is completed or still active interval.`Filter(eq)` |
| [IntervalStartUtc](Systems.Monitoring.DbResourceUtilization.md#intervalstartutc) | datetime | Start timestamp of the interval in UTC.`Required` `Filter(eq;ge;le)` |
| [LogicalReads](Systems.Monitoring.DbResourceUtilization.md#logicalreads) | int64 __nullable__ | Total logical reads executed during the interval. |
| [LogicalWrites](Systems.Monitoring.DbResourceUtilization.md#logicalwrites) | int64 __nullable__ |  Total logical writes executed during the interval. |
| [PhysicalReadsCount](Systems.Monitoring.DbResourceUtilization.md#physicalreadscount) | int64 __nullable__ | Total physical reads executed during the interval. |
| [PhysicalReadsMB](Systems.Monitoring.DbResourceUtilization.md#physicalreadsmb) | double __nullable__ | Total disk read volume (MB) during the interval. |
| [PhysicalReadsMBps](Systems.Monitoring.DbResourceUtilization.md#physicalreadsmbps) | double __nullable__ | Average disk read throughput (MB/s) during the interval. |
| [WaitCpuMs](Systems.Monitoring.DbResourceUtilization.md#waitcpums) | int64 __nullable__ | Total wait time (ms) due to CPU resource contention. |
| [WaitIoMs](Systems.Monitoring.DbResourceUtilization.md#waitioms) | int64 __nullable__ | Total wait time (ms) related to I/O operations. |
| [WaitLockMs](Systems.Monitoring.DbResourceUtilization.md#waitlockms) | int64 __nullable__ | Total wait time (ms) caused by locks or blocking. |
| [WaitMemoryMs](Systems.Monitoring.DbResourceUtilization.md#waitmemoryms) | int64 __nullable__ | Total wait time (ms) due to memory resource contention. |
| [WaitNetworkMs](Systems.Monitoring.DbResourceUtilization.md#waitnetworkms) | int64 __nullable__ | Total wait time (ms) caused by network transfer-related waits. |
| [WaitOtherMs](Systems.Monitoring.DbResourceUtilization.md#waitotherms) | int64 __nullable__ | Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network. |


## Attribute Details

### AvgCpuCores

Average CPU execution load, expressed in CPU cores (relative to 1 core).

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgMemoryPerQueryMB

Average memory (MB) used per query execution.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalCores

Average total load, expressed in CPU cores (relative to 1 core).

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgTotalQueryMemoryMB

Average total memory (MB) consumed by all concurrent query executions.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AvgWaitingCores

Average waiting load, expressed in CPU cores (relative to 1 core).

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionCount

Total number of executed queries during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionDurationMs

Total duration (ms) of all completed query executions in the interval.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionsPerSecond

Average number of queries executed per second.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalCompletionRatio

Ratio (0–1) indicating how much of the interval has elapsed. Values &lt; 1 mean the interval is still active and data is not final.

Type: **double __nullable__**  
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

Unique identifier of the runtime interval.`Filter(eq)`

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IntervalIsCompleted

Indicates whether this is completed or still active interval.`Filter(eq)`

Type: **boolean __nullable__**  
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

Total logical reads executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LogicalWrites

Total logical writes executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsCount

Total physical reads executed during the interval.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsMB

Total disk read volume (MB) during the interval.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PhysicalReadsMBps

Average disk read throughput (MB/s) during the interval.

Type: **double __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitCpuMs

Total wait time (ms) due to CPU resource contention.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitIoMs

Total wait time (ms) related to I/O operations.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitLockMs

Total wait time (ms) caused by locks or blocking.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitMemoryMs

Total wait time (ms) due to memory resource contention.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitNetworkMs

Total wait time (ms) caused by network transfer-related waits.

Type: **int64 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WaitOtherMs

Total wait time (ms) for events other than CPU, I/O, Lock, Memory, or Network.

Type: **int64 __nullable__**  
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

