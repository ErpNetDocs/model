---
uid: Systems.Bpm.ProcessGroups
---
# Systems.Bpm.ProcessGroups Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represents a node in the hierarchy of process groups. Entity: Bpm_Process_Groups

## Default Visualization
Default Display Text Format:  
_{Code}: {Name:T}_  
Default Search Member:  
_Code_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.ProcessGroups](Systems.Bpm.ProcessGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Bpm.ProcessGroups.md#code) | string (5) | Group code, unique within the parent group. `Required` `Filter(eq;like)` 
| [Id](Systems.Bpm.ProcessGroups.md#id) | guid |  
| [Name](Systems.Bpm.ProcessGroups.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | Multilanguage process group name. `Required` `Filter(eq;like)` 
| [Notes](Systems.Bpm.ProcessGroups.md#notes) | string (max) __nullable__ | Notes for this ProcessGroup. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Parent](Systems.Bpm.ProcessGroups.md#parent) | [ProcessGroups](Systems.Bpm.ProcessGroups.md) (nullable) | Parent process group in the hierarchy. null means this is a root group. `Filter(multi eq)` |


## Attribute Details

### Code

Group code, unique within the parent group. `Required` `Filter(eq;like)`

_Type_: **string (5)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **5**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Name

Multilanguage process group name. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Notes

Notes for this ProcessGroup.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  


## Reference Details

### Parent

Parent process group in the hierarchy. null means this is a root group. `Filter(multi eq)`

_Type_: **[ProcessGroups](Systems.Bpm.ProcessGroups.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Systems.Bpm.ProcessGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ProcessGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ProcessGroups?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ProcessGroups?$top=10>

