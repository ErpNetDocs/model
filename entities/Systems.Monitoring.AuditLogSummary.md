---
uid: Systems.Monitoring.AuditLogSummary
---
# Systems.Monitoring.AuditLogSummary (View)


Information about the count and the size of audit log entries, grouped by application name, event class, entity name and event time.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.AuditLogSummary  
Introduced In Version: 24.1.3.48  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.AuditLogEntries  
New name: Systems.Monitoring.AuditLogSummary  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ApplicationName}: {EventClass}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AuditLogSummary](Systems.Monitoring.AuditLogSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.AuditLogSummary.md#applicationname) | string (64) | The client application that triggered the events. Null when unknown or N/A.`Required` `Filter(eq;like)` `ORD` 
| [EntityName](Systems.Monitoring.AuditLogSummary.md#entityname) | string (64) | The entity, which is being referenced by the events. Null when unknown or N/A.`Required` `Filter(eq;like)` `ORD` 
| [EntriesCount](Systems.Monitoring.AuditLogSummary.md#entriescount) | int32 | Total number of audit log entries.`Required` `Filter(eq;ge;le)` `ORD` 
| [EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass) | [EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass) | The event primary classification, which shows the source of the events.`Required` `Filter(multi eq;like)` `ORD` `Inherited from Sys_Audit_Log_<br />Entries_Table.Event_Class` 
| [TotalSizeMB](Systems.Monitoring.AuditLogSummary.md#totalsizemb) | decimal (12, 3) | Total size of the audit log entries in megabytes.`Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Monitoring.AuditLogSummary.md#year) | string (30) | Year when the events occurred.`Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### ApplicationName

The client application that triggered the events. Null when unknown or N/A.`Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### EntityName

The entity, which is being referenced by the events. Null when unknown or N/A.`Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### EntriesCount

Total number of audit log entries.`Required` `Filter(eq;ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### EventClass

The event primary classification, which shows the source of the events.`Required` `Filter(multi eq;like)` `ORD` `Inherited from Sys_Audit_Log_Entries_Table.Event_Class`

Type: **[EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass)**  
Category: **System**  
Allowed values for the `EventClass`(Systems.Monitoring.AuditLogSummary.md#eventclass) data attribute  
Allowed Values (Systems.Monitoring.AuditLogSummaryRepository.EventClass Enum Members)  

| Value | Description |
| ---- | --- |
| Entity | Entity value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 0 <br /> Domain API Value: 'Entity' |
| Authentication | Authentication value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 1 <br /> Domain API Value: 'Authentication' |
| Server | Server value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 2 <br /> Domain API Value: 'Server' |

Inherited From: **Sys_Audit_Log_Entries_Table.Event_Class**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalSizeMB

Total size of the audit log entries in megabytes.`Required` `Filter(eq;ge;le)` `ORD`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Year

Year when the events occurred.`Required` `Filter(eq;like)` `ORD`

Type: **string (30)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_AuditLogSummary

Domain API Entity Type: 
Systems_Monitoring_AuditLogSummaryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_AuditLogSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_AuditLogSummary?$top=10>

