---
uid: Systems.Monitoring.ProcessInfo
---
# Systems.Monitoring.ProcessInfo (View)


Process information dynamic management view

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ProcessInfo  
Introduced In Version: 24.1.4.36  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.ProcessInfo  
New name: Systems.Monitoring.ProcessInfo  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ProcessId}: {ProcessName}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ProcessInfo](Systems.Monitoring.ProcessInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CPUUtilization](Systems.Monitoring.ProcessInfo.md#cpuutilization) | double | CPU utilization by the process in percents 
| [MemoryMB](Systems.Monitoring.ProcessInfo.md#memorymb) | decimal (12, 3) | The memory used by the process in Megabytes 
| [ProcessId](Systems.Monitoring.ProcessInfo.md#processid) | int32 | The id of process 
| [ProcessName](Systems.Monitoring.ProcessInfo.md#processname) | string (256) | The name of process 


## Attribute Details

### CPUUtilization

CPU utilization by the process in percents

Type: **double**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### MemoryMB

The memory used by the process in Megabytes

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### ProcessId

The id of process

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ProcessName

The name of process

Type: **string (256)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_ProcessInfo

Domain API Entity Type: 
Systems_Monitoring_ProcessInfoEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ProcessInfo?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ProcessInfo?$top=10>

