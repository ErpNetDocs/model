---
uid: Systems.Dmv.LicenseHistory
---
# Systems.Dmv.LicenseHistory View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Historical licensing events for the instance. Entity: Dmv_License_History (Introduced in version 24.1.3.88)
## Renamed
**New name:** [Systems.Monitoring.LicenseHistory](Systems.Monitoring.LicenseHistory.md)  



## Default Visualization
Default Display Text Format:  
_{LicensingEvent}: {LicensingDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.LicenseHistory](Systems.Dmv.LicenseHistory.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LicenseCode](Systems.Dmv.LicenseHistory.md#licensecode) | string (64) | The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)` 
| [LicenseCount](Systems.Dmv.LicenseHistory.md#licensecount) | int32 | The number of licenses given (+) or taken (-). `Required` `Filter(eq;ge;le)` 
| [LicenseDescription](Systems.Dmv.LicenseHistory.md#licensedescription) | string (max) | Description of the license code. `Required` 
| [LicenseEndDate](Systems.Dmv.LicenseHistory.md#licenseenddate) | date | The date (inclusive), until the license is active. `Required` `Filter(eq;ge;le)` 
| [LicenseScaleType](Systems.Dmv.LicenseHistory.md#licensescaletype) | string (64) | Denotes whether the license supports counts, different from 0 and 1. `Required` 
| [LicenseStartDate](Systems.Dmv.LicenseHistory.md#licensestartdate) | date | The date (inclusive), from which the license is active. `Required` `Filter(eq;ge;le)` 
| [LicensingDate](Systems.Dmv.LicenseHistory.md#licensingdate) | date | The date, when the license was issued. `Required` `Filter(eq;ge;le)` 
| [LicensingEvent](Systems.Dmv.LicenseHistory.md#licensingevent) | string (128) | Unique licensing event key. Can be used to group all license codes given with a single licensing event. `Required` 


## Attribute Details

### LicenseCode

The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### LicenseCount

The number of licenses given (+) or taken (-). `Required` `Filter(eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicenseDescription

Description of the license code. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### LicenseEndDate

The date (inclusive), until the license is active. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicenseScaleType

Denotes whether the license supports counts, different from 0 and 1. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### LicenseStartDate

The date (inclusive), from which the license is active. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicensingDate

The date, when the license was issued. `Required` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicensingEvent

Unique licensing event key. Can be used to group all license codes given with a single licensing event. `Required`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_LicenseHistory?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_LicenseHistory?$top=10>

