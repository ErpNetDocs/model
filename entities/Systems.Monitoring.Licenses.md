---
uid: Systems.Monitoring.Licenses
---
# Systems.Monitoring.Licenses (View)


The currently active licenses for the instance.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.Licenses  
Introduced In Version: 24.1.3.66  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.Licenses  
New name: Systems.Monitoring.Licenses  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {LicenseCode}: {LicenseDescription}  
Search Members:   
Category:  DynamicViews  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.Licenses](Systems.Monitoring.Licenses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LicenseCode](Systems.Monitoring.Licenses.md#licensecode) | string (64) | The code of the module or functionality, which is licensed. 
| [LicenseCount](Systems.Monitoring.Licenses.md#licensecount) | int32 | The current count (as of now) of active licenses. 
| [LicenseDescription](Systems.Monitoring.Licenses.md#licensedescription) | string (max) | Description of the license code. 
| [LicenseScaleType](Systems.Monitoring.Licenses.md#licensescaletype) | string (64) | Denotes whether the license supports counts, different from 0 and 1. 


## Attribute Details

### LicenseCode

The code of the module or functionality, which is licensed.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### LicenseCount

The current count (as of now) of active licenses.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicenseDescription

Description of the license code.

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### LicenseScaleType

Denotes whether the license supports counts, different from 0 and 1.

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_Licenses

Domain API Entity Type: 
Systems_Monitoring_LicensesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_Licenses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_Licenses?$top=10>

