---
uid: Systems.Monitoring.TableInfo
---
# Systems.Monitoring.TableInfo (View)


Information about the tables in the database.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.TableInfo  
Introduced In Version: 23.1.2.43  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.TableInfo  
New name: Systems.Monitoring.TableInfo  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {TableName}: {SizeMB}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.TableInfo](Systems.Monitoring.TableInfo.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [RowCount](Systems.Monitoring.TableInfo.md#rowcount) | int64 | Total number of rows[Required] [Filter(eq;ge;le)] [ORD] 
| [SizeMB](Systems.Monitoring.TableInfo.md#sizemb) | decimal (12, 3) | Total used size of the table in Megabytes.[Required] [Filter(eq;ge;le)] [ORD] 
| [TableName](Systems.Monitoring.TableInfo.md#tablename) | string (128) | The name of the table, for which we provide the data.[Required] [Filter(eq;like)] [ORD] 


## Attribute Details

### RowCount

Total number of rows[Required] [Filter(eq;ge;le)] [ORD]

Type: **int64**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### SizeMB

Total used size of the table in Megabytes.[Required] [Filter(eq;ge;le)] [ORD]

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TableName

The name of the table, for which we provide the data.[Required] [Filter(eq;like)] [ORD]

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_TableInfo

Domain API Entity Type: 
Systems_Monitoring_TableInfoEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_TableInfo?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_TableInfo?$top=10>

