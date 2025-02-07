---
uid: Systems.Dmv.ObjectFiles
---
# Systems.Dmv.ObjectFiles View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Information about object file sizes, grouped by entity type and creation time. Entity: Dmv_Object_Files (Introduced in version 24.1.3.46)
## Renamed
**New name:** [Systems.Monitoring.ObjectFiles](Systems.Monitoring.ObjectFiles.md)  



## Default Visualization
Default Display Text Format:  
_{EntityType}: {Year}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.ObjectFiles](Systems.Dmv.ObjectFiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvgFileSizeMB](Systems.Dmv.ObjectFiles.md#avgfilesizemb) | decimal (12, 3) | Average file size in megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [EntityType](Systems.Dmv.ObjectFiles.md#entitytype) | string (64) | The entity type to which the files are bound. `Required` `Filter(eq;like)` `ORD` 
| [FilesCount](Systems.Dmv.ObjectFiles.md#filescount) | int32 | Total number of files. `Required` `Filter(eq;ge;le)` `ORD` 
| [TotalSizeMB](Systems.Dmv.ObjectFiles.md#totalsizemb) | decimal (12, 3) | Total size of the files in megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Dmv.ObjectFiles.md#year) | string (30) | Year of files creation. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### AvgFileSizeMB

Average file size in megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### EntityType

The entity type to which the files are bound. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### FilesCount

Total number of files. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### TotalSizeMB

Total size of the files in megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Year

Year of files creation. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (30)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_ObjectFiles?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_ObjectFiles?$top=10>

