---
uid: Systems.Dmv.PrintImages
---
# Systems.Dmv.PrintImages View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Information about print sizes, grouped by document type and print type. Entity: Dmv_Print_Images (Introduced in version 24.1.0.15)
## Renamed
**New name:** [Systems.Monitoring.PrintImages](Systems.Monitoring.PrintImages.md)  



## Default Visualization
Default Display Text Format:  
_{PrintoutLayoutName}: {TypeName}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.PrintImages](Systems.Dmv.PrintImages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentEntityName](Systems.Dmv.PrintImages.md#documententityname) | string (64) | The entity name of the document type. `Required` `Filter(eq;like)` `ORD` 
| [PrintoutLayoutName](Systems.Dmv.PrintImages.md#printoutlayoutname) | string (64) | Printout layout name. `Required` `Filter(eq;like)` `ORD` 
| [PrintsCount](Systems.Dmv.PrintImages.md#printscount) | int32 | Total number of prints. `Required` `Filter(eq;ge;le)` `ORD` 
| [SizeMB](Systems.Dmv.PrintImages.md#sizemb) | decimal (12, 3) | Total size of the print in megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [TypeName](Systems.Dmv.PrintImages.md#typename) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the document type. `Required` `Filter(eq;like)` `ORD` 
| [UnitSizeMB](Systems.Dmv.PrintImages.md#unitsizemb) | decimal (12, 3) | Average print size in megabytes. `Required` `Filter(eq;ge;le)` `ORD` 
| [Year](Systems.Dmv.PrintImages.md#year) | string (30) | The year to which the current data refers. `Required` `Filter(eq;like)` `ORD` `Introduced in version 24.1.3.32` 


## Attribute Details

### DocumentEntityName

The entity name of the document type. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PrintoutLayoutName

Printout layout name. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PrintsCount

Total number of prints. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### SizeMB

Total size of the print in megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### TypeName

Name of the document type. `Required` `Filter(eq;like)` `ORD`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### UnitSizeMB

Average print size in megabytes. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **decimal (12, 3)**  
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

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_PrintImages?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_PrintImages?$top=10>

