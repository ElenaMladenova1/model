# Systems.Bpm.ExecutionSteps

Contains both historical and active steps in the execution of the business processes. Entity: Bpm_Execution_Steps

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.ExecutionSteps.md#Id) | guid |  
| [ExecutionState](Systems.Bpm.ExecutionSteps.md#ExecutionState) | int32 | Shows where the execution of the step has reached. 0=Ready; 10=Active; 20=Executing; 30=Completing; 40=Failing; 50=Terminating; 60=Completed; 70=Failed; 80=Terminated. [Required] [Default(0)] 
| [StartTime](Systems.Bpm.ExecutionSteps.md#StartTime) | datetime | The date and time when the step execution started. [Required] [Default(Now)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProcessElement](Systems.Bpm.ExecutionSteps.md#ProcessElement) | [Systems.Bpm.ProcessElements](Systems.Bpm.ProcessElements.md) | The process element, which is being executed for the instance. [Required] [Filter(multi eq)] |
| [ProcessInstance](Systems.Bpm.ExecutionSteps.md#ProcessInstance) | [Systems.Bpm.ProcessInstances](Systems.Bpm.ProcessInstances.md) | The process instance, which is being executed. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### ExecutionState

> Shows where the execution of the step has reached. 0=Ready; 10=Active; 20=Executing; 30=Completing; 40=Failing; 50=Terminating; 60=Completed; 70=Failed; 80=Terminated. [Required] [Default(0)]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### StartTime

> The date and time when the step execution started. [Required] [Default(Now)]

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  


## Reference Details

### ProcessElement

> The process element, which is being executed for the instance. [Required] [Filter(multi eq)]

_Type_: **[Systems.Bpm.ProcessElements](Systems.Bpm.ProcessElements.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ProcessInstance

> The process instance, which is being executed. [Required] [Filter(multi eq)]

_Type_: **[Systems.Bpm.ProcessInstances](Systems.Bpm.ProcessInstances.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Systems.Bpm.ExecutionSteps erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ExecutionSteps erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Bpm.ExecutionSteps erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ExecutionSteps?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ExecutionSteps?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Bpm_Execution_Steps?$top=10>
