---
uid: Systems.Monitoring.AuditLogSummary
---
# Systems.Monitoring.AuditLogSummary View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Information about the count and the size of audit log entries, grouped by application name, event class, entity name and event time. Entity: Dmv_Audit_Log_Entries (Introduced in version 24.1.3.48)

## Renames

Old name: **Systems.Dmv.AuditLogEntries**  
New name: **Systems.Monitoring.AuditLogSummary**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{ApplicationName}: {EventClass}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.AuditLogSummary](Systems.Monitoring.AuditLogSummary.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.AuditLogSummary.md#applicationname) | string (64) | The client application that triggered the events. Null when unknown or N/A. `Required` `Filter(eq;like)` `ORD` 
| [EntityName](Systems.Monitoring.AuditLogSummary.md#entityname) | string (64) | The entity, which is being referenced by the events. Null when unknown or N/A. `Required` `Filter(eq;like)` `ORD` 
| [EntriesCount](Systems.Monitoring.AuditLogSummary.md#entriescount) | int32 | Total number of audit log entries. `Required` `Filter(eq;ge;le)` `ORD` 
| [EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass) | [EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass) | The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events. `Required` `Filter(multi eq;like)` `ORD` `Inherited from Sys_Audit_Log_<br />Entries_Table.Event_Class` 
| [TotalSizeMB](Systems.Monitoring.AuditLogSummary.md#totalsizemb) | decimal (12, 3) | Total size of the audit log entries in megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Monitoring.AuditLogSummary.md#year) | string (30) | Year when the events occurred. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### ApplicationName

The client application that triggered the events. Null when unknown or N/A. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### EntityName

The entity, which is being referenced by the events. Null when unknown or N/A. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### EntriesCount

Total number of audit log entries. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### EventClass

The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events. `Required` `Filter(multi eq;like)` `ORD` `Inherited from Sys_Audit_Log_Entries_Table.Event_Class`

_Type_: **[EventClass](Systems.Monitoring.AuditLogSummary.md#eventclass)**  
_Category_: **System**  
Allowed values for the `EventClass`(Systems.Monitoring.AuditLogSummary.md#eventclass) data attribute  
_Allowed Values (Systems.Monitoring.AuditLogSummaryRepository.EventClass Enum Members)_  

| Value | Description |
| ---- | --- |
| Entity | Entity value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Entity' |
| Authentication | Authentication value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Authentication' |
| Server | Server value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Server' |

_Inherited From_: **Sys_Audit_Log_Entries_Table.Event_Class**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalSizeMB

Total size of the audit log entries in megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Year

Year when the events occurred. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_AuditLogSummary?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_AuditLogSummary?$top=10>

