---
uid: Systems.Dmv.TableInfo
---
# Systems.Dmv.TableInfo View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Information about the tables in the database. Entity: Dmv_Table_Info (Introduced in version 23.1.2.43)
## Renamed
**New name:** [Systems.Monitoring.TableInfo](Systems.Monitoring.TableInfo.md)  



## Default Visualization
Default Display Text Format:  
_{TableName}: {SizeMB}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.TableInfo](Systems.Dmv.TableInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [RowCount](Systems.Dmv.TableInfo.md#rowcount) | int64 | Total number of rows. `Required` `Filter(eq;ge;le)` `ORD` 
| [SizeMB](Systems.Dmv.TableInfo.md#sizemb) | decimal (12, 3) | Total used size of the table in Megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [TableName](Systems.Dmv.TableInfo.md#tablename) | string (128) | The name of the table, for which we provide the data. `Required` `Filter(eq;like)` `ORD` 


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
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_TableInfo?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_TableInfo?$top=10>

