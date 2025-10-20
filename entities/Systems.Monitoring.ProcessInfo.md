---
uid: Systems.Monitoring.ProcessInfo
---
# Systems.Monitoring.ProcessInfo View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Process information dynamic management view. Entity: Dmv_Process_Info (Introduced in version 24.1.4.36)

## Renames

Old name: **Systems.Dmv.ProcessInfo**  
New name: **Systems.Monitoring.ProcessInfo**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{ProcessId}: {ProcessName}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ProcessInfo](Systems.Monitoring.ProcessInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CPUUtilization](Systems.Monitoring.ProcessInfo.md#cpuutilization) | double | CPU utilization by the process in percents. `Required` `Filter(eq;ge;le)` `ORD` 
| [MemoryMB](Systems.Monitoring.ProcessInfo.md#memorymb) | decimal (12, 3) | The memory used by the process in Megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [ProcessId](Systems.Monitoring.ProcessInfo.md#processid) | int32 | The id of process. `Required` `Filter(eq)` 
| [ProcessName](Systems.Monitoring.ProcessInfo.md#processname) | string (256) | The name of process. `Required` `Filter(eq;like)` `ORD` 


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

Domain API Entity Set:
Systems_Monitoring_ProcessInfo

Domain API Entity Type:
Systems_Monitoring_ProcessInfoEntry

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_ProcessInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ProcessInfo?$top=10>

