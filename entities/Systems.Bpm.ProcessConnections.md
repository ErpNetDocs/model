---
uid: Systems.Bpm.ProcessConnections
---
# Systems.Bpm.ProcessConnections Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Contains the connections between process elements. Part of the process model. Entity: Bpm_Process_Connections

## Default Visualization
Default Display Text Format:  
_{Code}: {Name:T}_  
Default Search Member:  
_Code_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.Processes](Systems.Bpm.Processes.md)  
Aggregate Root:  
[Systems.Bpm.Processes](Systems.Bpm.Processes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Bpm.ProcessConnections.md#code) | string (64) | Connection code, unique within the process. Used as ID for XML serialization purposes. `Required` `Default(New Guid)` `Filter(eq;like)` 
| [ConditionFilterXml](Systems.Bpm.ProcessConnections.md#conditionfilterxml) | dataaccessfilter __nullable__ | When not null, specifies that the flow will be followed only if the condition is matched by the current values in the process instance. `Filter(eq;like)` 
| [Id](Systems.Bpm.ProcessConnections.md#id) | guid |  
| [IsDefault](Systems.Bpm.ProcessConnections.md#isdefault) | boolean | Denotes this flow as the default sequence flow. It is taken only when all other flows are not valid. For example, gateways usually are followed by several conditional flows and one default flow. `Required` `Default(false)` `Filter(eq)` 
| [Name](Systems.Bpm.ProcessConnections.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | Multilanguage connection name. `Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Process](Systems.Bpm.ProcessConnections.md#process) | [Processes](Systems.Bpm.Processes.md) | The process version to which this connection belongs. `Required` `Filter(multi eq)` `Owner` |
| [SourceProcessNode](Systems.Bpm.ProcessConnections.md#sourceprocessnode) | [ProcessNodes](Systems.Bpm.ProcessNodes.md) | The element, from which the connection starts. The element should be in the same process as the connection. `Required` `Filter(multi eq)` |
| [TargetProcessNode](Systems.Bpm.ProcessConnections.md#targetprocessnode) | [ProcessNodes](Systems.Bpm.ProcessNodes.md) | The element, at which the connection ends. The element should be in the same process as the connection. `Required` `Filter(multi eq)` |


## Attribute Details

### Code

Connection code, unique within the process. Used as ID for XML serialization purposes. `Required` `Default(New Guid)` `Filter(eq;like)`

_Type_: **string (64)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: **NewGuid**  

### ConditionFilterXml

When not null, specifies that the flow will be followed only if the condition is matched by the current values in the process instance. `Filter(eq;like)`

_Type_: **dataaccessfilter __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsDefault

Denotes this flow as the default sequence flow. It is taken only when all other flows are not valid. For example, gateways usually are followed by several conditional flows and one default flow. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Name

Multilanguage connection name. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


## Reference Details

### Process

The process version to which this connection belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Processes](Systems.Bpm.Processes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### SourceProcessNode

The element, from which the connection starts. The element should be in the same process as the connection. `Required` `Filter(multi eq)`

_Type_: **[ProcessNodes](Systems.Bpm.ProcessNodes.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### TargetProcessNode

The element, at which the connection ends. The element should be in the same process as the connection. `Required` `Filter(multi eq)`

_Type_: **[ProcessNodes](Systems.Bpm.ProcessNodes.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Systems.Bpm.ProcessConnections erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ProcessConnections erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ProcessConnections?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ProcessConnections?$top=10>

