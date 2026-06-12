---
uid: Systems.Bpm.ProcessNodeEvents
---
# Systems.Bpm.ProcessNodeEvents Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Abstract root of all process node events. Currently - not used. Entity: Bpm_Process_Node_Events

## Default Visualization
Default Display Text Format:  
_{Id}_  
Default Search Member:  
_Id_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.ProcessNodeEvents](Systems.Bpm.ProcessNodeEvents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BoundaryOfProcessNodeId](Systems.Bpm.ProcessNodeEvents.md#boundaryofprocessnodeid) | guid __nullable__ | When the event is boundary, contains the node to which the event is bound. Otherwise contains null. `Filter(multi eq)` 
| [EventKey](Systems.Bpm.ProcessNodeEvents.md#eventkey) | string (128) | The unique event key, which is thrown or caught. `Required` 
| [EventType](Systems.Bpm.ProcessNodeEvents.md#eventtype) | string (1) | Event type. S=Start, T=Intermediate Throw, C=Intermediate Catch, B=Boundary, E=End. `Required` 
| [Id](Systems.Bpm.ProcessNodeEvents.md#id) | guid |  
| [IsCancel](Systems.Bpm.ProcessNodeEvents.md#iscancel) | boolean | True if this is cancel event. `Required` 
| [IsCompensation](Systems.Bpm.ProcessNodeEvents.md#iscompensation) | boolean | True if this is compensation event. `Required` 
| [IsError](Systems.Bpm.ProcessNodeEvents.md#iserror) | boolean | True if this is error event. `Required` 
| [IsEscalation](Systems.Bpm.ProcessNodeEvents.md#isescalation) | boolean | True if this is escalation event. `Required` 
| [IsMessage](Systems.Bpm.ProcessNodeEvents.md#ismessage) | boolean | True if this is message event. `Required` 
| [IsSignal](Systems.Bpm.ProcessNodeEvents.md#issignal) | boolean | True if this is signal event. `Required` 
| [IsTimer](Systems.Bpm.ProcessNodeEvents.md#istimer) | boolean | True if this is timer event. `Required` 
| [ProcessNodeId](Systems.Bpm.ProcessNodeEvents.md#processnodeid) | guid | The node of this node event. `Required` `Filter(multi eq)` 


## Attribute Details

### BoundaryOfProcessNodeId

When the event is boundary, contains the node to which the event is bound. Otherwise contains null. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Supported Filters_: **Equals, EqualsIn**  

### EventKey

The unique event key, which is thrown or caught. `Required`

_Type_: **string (128)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  

### EventType

Event type. S=Start, T=Intermediate Throw, C=Intermediate Catch, B=Boundary, E=End. `Required`

_Type_: **string (1)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **1**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsCancel

True if this is cancel event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsCompensation

True if this is compensation event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsError

True if this is error event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsEscalation

True if this is escalation event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsMessage

True if this is message event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsSignal

True if this is signal event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsTimer

True if this is timer event. `Required`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ProcessNodeId

The node of this node event. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodeEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodeEvents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ProcessNodeEvents?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ProcessNodeEvents?$top=10>

