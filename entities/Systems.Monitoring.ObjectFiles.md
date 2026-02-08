---
uid: Systems.Monitoring.ObjectFiles
---
# Systems.Monitoring.ObjectFiles (View)


Information about object file sizes, grouped by entity type and creation time.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ObjectFiles  
Introduced In Version: 24.1.3.46  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.ObjectFiles  
New name: Systems.Monitoring.ObjectFiles  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {EntityType}: {Year}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ObjectFiles](Systems.Monitoring.ObjectFiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvgFileSizeMB](Systems.Monitoring.ObjectFiles.md#avgfilesizemb) | decimal (12, 3) | Average file size in megabytes`Required` `Filter(eq;ge;le)` `ORD` 
| [EntityType](Systems.Monitoring.ObjectFiles.md#entitytype) | string (64) | The entity type to which the files are bound`Required` `Filter(eq;like)` `ORD` 
| [FilesCount](Systems.Monitoring.ObjectFiles.md#filescount) | int32 | Total number of files`Required` `Filter(eq;ge;le)` `ORD` 
| [TotalSizeMB](Systems.Monitoring.ObjectFiles.md#totalsizemb) | decimal (12, 3) | Total size of the files in megabytes`Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Monitoring.ObjectFiles.md#year) | string (30) | Year of files creation`Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### AvgFileSizeMB

Average file size in megabytes`Required` `Filter(eq;ge;le)` `ORD`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### EntityType

The entity type to which the files are bound`Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### FilesCount

Total number of files`Required` `Filter(eq;ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TotalSizeMB

Total size of the files in megabytes`Required` `Filter(eq;ge;le)` `ORD`

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Year

Year of files creation`Required` `Filter(eq;like)` `ORD`

Type: **string (30)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_ObjectFiles

Domain API Entity Type: 
Systems_Monitoring_ObjectFilesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ObjectFiles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ObjectFiles?$top=10>

