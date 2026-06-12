---
uid: Systems.Dmv.CurrentLicense
---
# Systems.Dmv.CurrentLicense View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Dynaimc management view, providing license information. Entity: Dmv_Current_License (Introduced in version 24.1.3.85)

## Default Visualization
Default Display Text Format:  
_{StartDate}: {ExpiryDate}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.CurrentLicense](Systems.Dmv.CurrentLicense.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExpiryDate](Systems.Dmv.CurrentLicense.md#expirydate) | datetime | When the license expires. `Required` `Filter(ge;le)` 
| [LicenseString](Systems.Dmv.CurrentLicense.md#licensestring) | string (max) | The license string. `Required` 
| [StartDate](Systems.Dmv.CurrentLicense.md#startdate) | datetime | The start date of the license. `Required` `Filter(ge;le)` 


## Attribute Details

### ExpiryDate

When the license expires. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LicenseString

The license string. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### StartDate

The start date of the license. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_CurrentLicense?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_CurrentLicense?$top=10>

