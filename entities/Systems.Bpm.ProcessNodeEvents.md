# Systems.Bpm.ProcessNodeEvents

Abstract root of all process node events. Currently - not used. Entity: Bpm_Process_Node_Events

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.ProcessNodeEvents.md#Id) | guid |  
| [BoundaryOfProcessNodeId](Systems.Bpm.ProcessNodeEvents.md#BoundaryOfProcessNodeId) | guid (nullable) | When the event is boundary, contains the node to which the event is bound. Otherwise contains null. [Filter(multi eq)] 
| [EventKey](Systems.Bpm.ProcessNodeEvents.md#EventKey) | string | The unique event key, which is thrown or caught. [Required] 
| [EventType](Systems.Bpm.ProcessNodeEvents.md#EventType) | string | Event type. S=Start, T=Intermediate Throw, C=Intermediate Catch, B=Boundary, E=End. [Required] 
| [IsCancel](Systems.Bpm.ProcessNodeEvents.md#IsCancel) | boolean | True if this is cancel event. [Required] 
| [IsCompensation](Systems.Bpm.ProcessNodeEvents.md#IsCompensation) | boolean | True if this is compensation event. [Required] 
| [IsError](Systems.Bpm.ProcessNodeEvents.md#IsError) | boolean | True if this is error event. [Required] 
| [IsEscalation](Systems.Bpm.ProcessNodeEvents.md#IsEscalation) | boolean | True if this is escalation event. [Required] 
| [IsMessage](Systems.Bpm.ProcessNodeEvents.md#IsMessage) | boolean | True if this is message event. [Required] 
| [IsSignal](Systems.Bpm.ProcessNodeEvents.md#IsSignal) | boolean | True if this is signal event. [Required] 
| [IsTimer](Systems.Bpm.ProcessNodeEvents.md#IsTimer) | boolean | True if this is timer event. [Required] 
| [ProcessNodeId](Systems.Bpm.ProcessNodeEvents.md#ProcessNodeId) | guid | The node of this node event. [Required] [Filter(multi eq)] 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### BoundaryOfProcessNodeId

> When the event is boundary, contains the node to which the event is bound. Otherwise contains null. [Filter(multi eq)]

_Type_: **guid (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### EventKey

> The unique event key, which is thrown or caught. [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### EventType

> Event type. S=Start, T=Intermediate Throw, C=Intermediate Catch, B=Boundary, E=End. [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsCancel

> True if this is cancel event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsCompensation

> True if this is compensation event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsError

> True if this is error event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsEscalation

> True if this is escalation event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsMessage

> True if this is message event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsSignal

> True if this is signal event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsTimer

> True if this is timer event. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ProcessNodeId

> The node of this node event. [Required] [Filter(multi eq)]

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodeEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodeEvents erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Bpm.ProcessNodeEvents erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ProcessNodeEvents?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ProcessNodeEvents?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Bpm_Process_Node_Events?$top=10>
