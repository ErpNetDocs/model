---
uid: Systems.Monitoring.TableInfo
---
# Systems.Monitoring.TableInfo View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Information about the tables in the database. Entity: Dmv_Table_Info (Introduced in version 23.1.2.43)

## Renames

Old name: **Systems.Dmv.TableInfo**  
New name: **Systems.Monitoring.TableInfo**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{TableName}: {SizeMB}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.TableInfo](Systems.Monitoring.TableInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [RowCount](Systems.Monitoring.TableInfo.md#rowcount) | int64 | Total number of rows. `Required` `Filter(eq;ge;le)` `ORD` 
| [SizeMB](Systems.Monitoring.TableInfo.md#sizemb) | decimal (12, 3) | Total used size of the table in Megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [TableName](Systems.Monitoring.TableInfo.md#tablename) | string (128) | The name of the table, for which we provide the data. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### RowCount

Total number of rows. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int64**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### SizeMB

Total used size of the table in Megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### TableName

The name of the table, for which we provide the data. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_TableInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_TableInfo?$top=10>

