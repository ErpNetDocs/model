---
uid: Systems.Monitoring.InstanceParameters
---
# Systems.Monitoring.InstanceParameters (View)


Parameters for this instance

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.InstanceParameters  
Introduced In Version: 24.1.1.68  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.InstanceParameters  
New name: Systems.Monitoring.InstanceParameters  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {ParameterName}: {ParameterValue}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.InstanceParameters](Systems.Monitoring.InstanceParameters.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ParameterName](Systems.Monitoring.InstanceParameters.md#parametername) | string (256) | Name of parameter[Required] [Filter(multi eq)] 
| [ParameterValue](Systems.Monitoring.InstanceParameters.md#parametervalue) | string (256) | Value of parameter[Required] 


## Attribute Details

### ParameterName

Name of parameter[Required] [Filter(multi eq)]

Type: **string (256)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### ParameterValue

Value of parameter[Required]

Type: **string (256)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Monitoring_InstanceParameters

Domain API Entity Type: 
Systems_Monitoring_InstanceParametersEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_InstanceParameters?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_InstanceParameters?$top=10>

