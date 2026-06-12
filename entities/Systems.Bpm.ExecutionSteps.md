---
uid: Systems.Bpm.ExecutionSteps
---
# Systems.Bpm.ExecutionSteps Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Contains both historical and active steps in the execution of the business processes. Entity: Bpm_Execution_Steps

## Default Visualization
Default Display Text Format:  
_{Id}_  
Default Search Member:  
_Id_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.ExecutionSteps](Systems.Bpm.ExecutionSteps.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExecutionState](Systems.Bpm.ExecutionSteps.md#executionstate) | int32 | Shows where the execution of the step has reached. 0=Ready; 10=Active; 20=Executing; 30=Completing; 40=Failing; 50=Terminating; 60=Completed; 70=Failed; 80=Terminated. `Required` `Default(0)` 
| [Id](Systems.Bpm.ExecutionSteps.md#id) | guid |  
| [StartTime](Systems.Bpm.ExecutionSteps.md#starttime) | datetime | The date and time when the step execution started. `Required` `Default(Now)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProcessElement](Systems.Bpm.ExecutionSteps.md#processelement) | [ProcessElements](Systems.Bpm.ProcessElements.md) | The process element, which is being executed for the instance. `Required` `Filter(multi eq)` |
| [ProcessInstance](Systems.Bpm.ExecutionSteps.md#processinstance) | [ProcessInstances](Systems.Bpm.ProcessInstances.md) | The process instance, which is being executed. `Required` `Filter(multi eq)` |


## Attribute Details

### ExecutionState

Shows where the execution of the step has reached. 0=Ready; 10=Active; 20=Executing; 30=Completing; 40=Failing; 50=Terminating; 60=Completed; 70=Failed; 80=Terminated. `Required` `Default(0)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### StartTime

The date and time when the step execution started. `Required` `Default(Now)`

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  


## Reference Details

### ProcessElement

The process element, which is being executed for the instance. `Required` `Filter(multi eq)`

_Type_: **[ProcessElements](Systems.Bpm.ProcessElements.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### ProcessInstance

The process instance, which is being executed. `Required` `Filter(multi eq)`

_Type_: **[ProcessInstances](Systems.Bpm.ProcessInstances.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Systems.Bpm.ExecutionSteps erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ExecutionSteps erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ExecutionSteps?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ExecutionSteps?$top=10>

