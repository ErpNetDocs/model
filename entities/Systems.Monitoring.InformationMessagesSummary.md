---
uid: Systems.Monitoring.InformationMessagesSummary
---
# Systems.Monitoring.InformationMessagesSummary (View)


Information abount types of information messages

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.InformationMessagesSummary  
Introduced In Version: 24.1.1.68  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.InformationMessages  
New name: Systems.Monitoring.InformationMessagesSummary  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Process}: {Count}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.InformationMessagesSummary](Systems.Monitoring.InformationMessagesSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Count](Systems.Monitoring.InformationMessagesSummary.md#count) | int32 | Total number of messages. `Required` `Filter(eq;ge;le)` `ORD` 
| [Process](Systems.Monitoring.InformationMessagesSummary.md#process) | string (254) | Process description for message. `Required` `Filter(eq;like)` `ORD` 
| [SizeMB](Systems.Monitoring.InformationMessagesSummary.md#sizemb) | int64 | Total used size for message type in Megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Monitoring.InformationMessagesSummary.md#year) | string (30) | The year to which the current data refers. `Required` `Filter(eq;like)` `ORD` `Introduced in version 24.1.3.32` 


## Attribute Details

### Count

Total number of messages. `Required` `Filter(eq;ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Process

Process description for message. `Required` `Filter(eq;like)` `ORD`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SizeMB

Total used size for message type in Megabytes. `Required` `Filter(eq;ge;le)` `ORD`

Type: **int64**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Year

The year to which the current data refers. `Required` `Filter(eq;like)` `ORD` `Introduced in version 24.1.3.32`

Type: **string (30)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_InformationMessagesSummary

Domain API Entity Type: 
Systems_Monitoring_InformationMessagesSummaryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_InformationMessagesSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_InformationMessagesSummary?$top=10>

