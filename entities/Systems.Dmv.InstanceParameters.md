---
uid: Systems.Dmv.InstanceParameters
---
# Systems.Dmv.InstanceParameters View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Parameters for this instance. Entity: Dmv_Instance_Parameters (Introduced in version 24.1.1.68)
## Renamed
**New name:** [Systems.Monitoring.InstanceParameters](Systems.Monitoring.InstanceParameters.md)  



## Default Visualization
Default Display Text Format:  
_{ParameterName}: {ParameterValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.InstanceParameters](Systems.Dmv.InstanceParameters.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ParameterName](Systems.Dmv.InstanceParameters.md#parametername) | string (256) | Name of parameter. `Required` `Filter(multi eq)` 
| [ParameterValue](Systems.Dmv.InstanceParameters.md#parametervalue) | string (256) | Value of parameter. `Required` 


## Attribute Details

### ParameterName

Name of parameter. `Required` `Filter(multi eq)`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### ParameterValue

Value of parameter. `Required`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_InstanceParameters?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_InstanceParameters?$top=10>

