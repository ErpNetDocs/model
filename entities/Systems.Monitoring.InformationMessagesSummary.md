---
uid: Systems.Monitoring.InformationMessagesSummary
---
# Systems.Monitoring.InformationMessagesSummary View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Information abount types of information messages. Entity: Dmv_Information_Messages (Introduced in version 24.1.1.68)

## Renames

Old name: **Systems.Dmv.InformationMessages**  
New name: **Systems.Monitoring.InformationMessagesSummary**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Process}: {Count}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

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

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Process

Process description for message. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### SizeMB

Total used size for message type in Megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int64**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Year

The year to which the current data refers. `Required` `Filter(eq;like)` `ORD` `Introduced in version 24.1.3.32`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_InformationMessagesSummary

Domain API Entity Type: 
Systems_Monitoring_InformationMessagesSummaryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_InformationMessagesSummary?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_InformationMessagesSummary?$top=10>

