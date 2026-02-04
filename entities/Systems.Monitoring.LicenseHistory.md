---
uid: Systems.Monitoring.LicenseHistory
---
# Systems.Monitoring.LicenseHistory (View)


Historical licensing events for the instance.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.LicenseHistory  
Introduced In Version: 24.1.3.88  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.LicenseHistory  
New name: Systems.Monitoring.LicenseHistory  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {LicensingEvent}: {LicensingDate}  
Search Members:   
Category:  DynamicViews  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.LicenseHistory](Systems.Monitoring.LicenseHistory.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LicenseCode](Systems.Monitoring.LicenseHistory.md#licensecode) | string (64) | The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)` 
| [LicenseCount](Systems.Monitoring.LicenseHistory.md#licensecount) | int32 | The number of licenses given (+) or taken (-). `Required` `Filter(eq;ge;le)` 
| [LicenseDescription](Systems.Monitoring.LicenseHistory.md#licensedescription) | string (max) | Description of the license code. `Required` 
| [LicenseEndDate](Systems.Monitoring.LicenseHistory.md#licenseenddate) | date | The date (inclusive), until the license is active. `Required` `Filter(eq;ge;le)` 
| [LicenseScaleType](Systems.Monitoring.LicenseHistory.md#licensescaletype) | string (64) | Denotes whether the license supports counts, different from 0 and 1. `Required` 
| [LicenseStartDate](Systems.Monitoring.LicenseHistory.md#licensestartdate) | date | The date (inclusive), from which the license is active. `Required` `Filter(eq;ge;le)` 
| [LicensingDate](Systems.Monitoring.LicenseHistory.md#licensingdate) | date | The date, when the license was issued. `Required` `Filter(eq;ge;le)` 
| [LicensingEvent](Systems.Monitoring.LicenseHistory.md#licensingevent) | string (128) | Unique licensing event key. Can be used to group all license codes given with a single licensing event. `Required` 


## Attribute Details

### LicenseCode

The code of the module or functionality, which is licensed. `Required` `Filter(multi eq;like)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### LicenseCount

The number of licenses given (+) or taken (-). `Required` `Filter(eq;ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicenseDescription

Description of the license code. `Required`

Type: **string (max)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### LicenseEndDate

The date (inclusive), until the license is active. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicenseScaleType

Denotes whether the license supports counts, different from 0 and 1. `Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### LicenseStartDate

The date (inclusive), from which the license is active. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicensingDate

The date, when the license was issued. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LicensingEvent

Unique licensing event key. Can be used to group all license codes given with a single licensing event. `Required`

Type: **string (128)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_LicenseHistory

Domain API Entity Type: 
Systems_Monitoring_LicenseHistoryEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_LicenseHistory?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_LicenseHistory?$top=10>

