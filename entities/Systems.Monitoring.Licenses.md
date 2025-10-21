---
uid: Systems.Monitoring.Licenses
---
# Systems.Monitoring.Licenses View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

The currently active licenses for the instance. Entity: Dmv_Licenses (Introduced in version 24.1.3.66)

## Renames

Old name: **Systems.Dmv.Licenses**  
New name: **Systems.Monitoring.Licenses**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{LicenseCode}: {LicenseDescription}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.Licenses](Systems.Monitoring.Licenses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LicenseCode](Systems.Monitoring.Licenses.md#licensecode) | string (64) | The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)` `Introduced in version 24.1.3.88` 
| [LicenseCount](Systems.Monitoring.Licenses.md#licensecount) | int32 | The current count (as of now) of active licenses. `Required` `Filter(eq;ge;le)` `Introduced in version 24.1.3.88` 
| [LicenseDescription](Systems.Monitoring.Licenses.md#licensedescription) | string (max) | Description of the license code. `Required` `Introduced in version 24.1.3.88` 
| [LicenseScaleType](Systems.Monitoring.Licenses.md#licensescaletype) | string (64) | Denotes whether the license supports counts, different from 0 and 1. `Required` `Introduced in version 24.1.3.88` 


## Attribute Details

### LicenseCode

The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)` `Introduced in version 24.1.3.88`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### LicenseCount

The current count (as of now) of active licenses. `Required` `Filter(eq;ge;le)` `Introduced in version 24.1.3.88`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicenseDescription

Description of the license code. `Required` `Introduced in version 24.1.3.88`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### LicenseScaleType

Denotes whether the license supports counts, different from 0 and 1. `Required` `Introduced in version 24.1.3.88`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_Licenses

Domain API Entity Type: 
Systems_Monitoring_LicensesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_Licenses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_Licenses?$top=10>

