---
uid: Systems.Dmv.ProcessInfo
---
# Systems.Dmv.ProcessInfo View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Process information dynamic management view. Entity: Dmv_Process_Info (Introduced in version 24.1.4.36)
## Renamed
**New name:** [Systems.Monitoring.ProcessInfo](Systems.Monitoring.ProcessInfo.md)  



## Default Visualization
Default Display Text Format:  
_{ProcessId}: {ProcessName}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.ProcessInfo](Systems.Dmv.ProcessInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CPUUtilization](Systems.Dmv.ProcessInfo.md#cpuutilization) | double | CPU utilization by the process in percents. `Required` `Filter(eq;ge;le)` `ORD` 
| [MemoryMB](Systems.Dmv.ProcessInfo.md#memorymb) | decimal (12, 3) | The memory used by the process in Megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [ProcessId](Systems.Dmv.ProcessInfo.md#processid) | int32 | The id of process. `Required` `Filter(eq)` 
| [ProcessName](Systems.Dmv.ProcessInfo.md#processname) | string (256) | The name of process. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### CPUUtilization

CPU utilization by the process in percents. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### MemoryMB

The memory used by the process in Megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### ProcessId

The id of process. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ProcessName

The name of process. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_ProcessInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_ProcessInfo?$top=10>

