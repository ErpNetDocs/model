---
uid: Systems.Monitoring.PrintImages
---
# Systems.Monitoring.PrintImages (View)


Information about print sizes, grouped by document type and print type.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.PrintImages  
Introduced In Version: 24.1.0.15  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.PrintImages  
New name: Systems.Monitoring.PrintImages  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {PrintoutLayoutName}: {TypeName}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.PrintImages](Systems.Monitoring.PrintImages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentEntityName](Systems.Monitoring.PrintImages.md#documententityname) | string (64) | The entity name of the document type. 
| [PrintoutLayoutName](Systems.Monitoring.PrintImages.md#printoutlayoutname) | string (64) | Printout layout name. 
| [PrintsCount](Systems.Monitoring.PrintImages.md#printscount) | int32 | Total number of prints. 
| [SizeMB](Systems.Monitoring.PrintImages.md#sizemb) | decimal (12, 3) | Total size of the print in megabytes. 
| [TypeName](Systems.Monitoring.PrintImages.md#typename) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the document type. 
| [UnitSizeMB](Systems.Monitoring.PrintImages.md#unitsizemb) | decimal (12, 3) | Average print size in megabytes. 
| [Year](Systems.Monitoring.PrintImages.md#year) | string (30) | The year to which the current data refers. 


## Attribute Details

### DocumentEntityName

The entity name of the document type.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PrintoutLayoutName

Printout layout name.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PrintsCount

Total number of prints.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### SizeMB

Total size of the print in megabytes.

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### TypeName

Name of the document type.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### UnitSizeMB

Average print size in megabytes.

Type: **decimal (12, 3)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Year

The year to which the current data refers.

Type: **string (30)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_PrintImages

Domain API Entity Type: 
Systems_Monitoring_PrintImagesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_PrintImages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_PrintImages?$top=10>

