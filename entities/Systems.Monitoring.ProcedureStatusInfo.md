---
uid: Systems.Monitoring.ProcedureStatusInfo
---
# Systems.Monitoring.ProcedureStatusInfo (View)


Shows the currently running and completed in the last five minutes procedures to the database.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ProcedureStatusInfo  
Introduced In Version: 23.1.1.53  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.ProcedureStatusInfo  
New name: Systems.Monitoring.ProcedureStatusInfo  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {StartTime}: {User}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ProcedureStatusInfo](Systems.Monitoring.ProcedureStatusInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Completed](Systems.Monitoring.ProcedureStatusInfo.md#completed) | boolean | True if the procedure is completed.[Required] [Filter(eq)] [ORD] 
| [ElapsedMin](Systems.Monitoring.ProcedureStatusInfo.md#elapsedmin) | string (64) | The elapsed minutes of the procedure at the time of the request.[Required] [Filter(ge;le)] [ORD] 
| [ElapsedPercent](Systems.Monitoring.ProcedureStatusInfo.md#elapsedpercent) | double | The elapsed percent of the procedure at the time of the request.[Required] [Filter(ge;le)] [ORD] 
| [EndTime](Systems.Monitoring.ProcedureStatusInfo.md#endtime) | string (64) | The end time of the procedure.[Required] [Filter(ge;le)] [ORD] 
| [Error](Systems.Monitoring.ProcedureStatusInfo.md#error) | string (128) | If not null, this is the text of the exception that occured during the procedure execution.[Required] [ORD] 
| [Procedure](Systems.Monitoring.ProcedureStatusInfo.md#procedure) | string (128) | The name of the procedure.[Required] [Filter(eq;like)] [ORD] 
| [Properties](Systems.Monitoring.ProcedureStatusInfo.md#properties) | string (128) | List of procedure status properties.[Required] [ORD] 
| [StartTime](Systems.Monitoring.ProcedureStatusInfo.md#starttime) | string (64) | The start time of the procedure.[Required] [Filter(ge;le)] [ORD] 
| [User](Systems.Monitoring.ProcedureStatusInfo.md#user) | string (128) | The user started the procedure.[Required] [Filter(eq;like)] [ORD] 


## Attribute Details

### Completed

True if the procedure is completed.[Required] [Filter(eq)] [ORD]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### ElapsedMin

The elapsed minutes of the procedure at the time of the request.[Required] [Filter(ge;le)] [ORD]

Type: **string (64)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ElapsedPercent

The elapsed percent of the procedure at the time of the request.[Required] [Filter(ge;le)] [ORD]

Type: **double**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### EndTime

The end time of the procedure.[Required] [Filter(ge;le)] [ORD]

Type: **string (64)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Error

If not null, this is the text of the exception that occured during the procedure execution.[Required] [ORD]

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Procedure

The name of the procedure.[Required] [Filter(eq;like)] [ORD]

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Properties

List of procedure status properties.[Required] [ORD]

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### StartTime

The start time of the procedure.[Required] [Filter(ge;le)] [ORD]

Type: **string (64)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### User

The user started the procedure.[Required] [Filter(eq;like)] [ORD]

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_ProcedureStatusInfo

Domain API Entity Type: 
Systems_Monitoring_ProcedureStatusInfoEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ProcedureStatusInfo?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ProcedureStatusInfo?$top=10>

