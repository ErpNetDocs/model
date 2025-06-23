---
uid: Systems.Monitoring.ProcedureStatusInfo
---
# Systems.Monitoring.ProcedureStatusInfo View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Dynamic management view for long running procedures. Entity: Dmv_Procedure_Status_Info (Introduced in version 23.1.1.53)

## Renames

Old name: **Systems.Dmv.ProcedureStatusInfo**  
New name: **Systems.Monitoring.ProcedureStatusInfo**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{StartTime}: {User}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ProcedureStatusInfo](Systems.Monitoring.ProcedureStatusInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Completed](Systems.Monitoring.ProcedureStatusInfo.md#completed) | boolean | True if the procedure is completed. `Required` `Filter(eq)` `ORD` 
| [ElapsedMin](Systems.Monitoring.ProcedureStatusInfo.md#elapsedmin) | string (64) | The elapsed minutes of the procedure at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [ElapsedPercent](Systems.Monitoring.ProcedureStatusInfo.md#elapsedpercent) | double | The elapsed percent of the procedure at the time of the request. `Required` `Filter(ge;le)` `ORD` 
| [EndTime](Systems.Monitoring.ProcedureStatusInfo.md#endtime) | string (64) | The end time of the procedure. `Required` `Filter(ge;le)` `ORD` 
| [Error](Systems.Monitoring.ProcedureStatusInfo.md#error) | string (128) | If not null, this is the text of the exception that occured during the procedure execution. `Required` `ORD` 
| [Procedure](Systems.Monitoring.ProcedureStatusInfo.md#procedure) | string (128) | The name of the procedure. `Required` `Filter(eq;like)` `ORD` 
| [Properties](Systems.Monitoring.ProcedureStatusInfo.md#properties) | string (128) | List of procedure status properties. `Required` `ORD` 
| [StartTime](Systems.Monitoring.ProcedureStatusInfo.md#starttime) | string (64) | The start time of the procedure. `Required` `Filter(ge;le)` `ORD` 
| [User](Systems.Monitoring.ProcedureStatusInfo.md#user) | string (128) | The user started the procedure. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### Completed

True if the procedure is completed. `Required` `Filter(eq)` `ORD`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### ElapsedMin

The elapsed minutes of the procedure at the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ElapsedPercent

The elapsed percent of the procedure at the time of the request. `Required` `Filter(ge;le)` `ORD`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### EndTime

The end time of the procedure. `Required` `Filter(ge;le)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Error

If not null, this is the text of the exception that occured during the procedure execution. `Required` `ORD`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Procedure

The name of the procedure. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Properties

List of procedure status properties. `Required` `ORD`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### StartTime

The start time of the procedure. `Required` `Filter(ge;le)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### User

The user started the procedure. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_ProcedureStatusInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ProcedureStatusInfo?$top=10>

