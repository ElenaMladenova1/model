---
uid: Systems.Bpm.ProcessNodes
---
# Systems.Bpm.ProcessNodes

Contains the flow Nodes of the process model. Entity: Bpm_Process_Nodes

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Bpm.ProcessNodes.md#code) | string | Node code, unique within the process. Used as ID for XML serialization purposes. [Required] [Filter(eq;like)] 
| [Id](Systems.Bpm.ProcessNodes.md#id) | guid |  
| [InstructionsHtml](Systems.Bpm.ProcessNodes.md#instructionshtml) | string (nullable) | Detailed instructions to the executor in HTML format. [Filter(eq;like)] 
| [Name](Systems.Bpm.ProcessNodes.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | Multilanguage process name. [Required] [Filter(eq;like)] 
| [NodeType](Systems.Bpm.ProcessNodes.md#nodetype) | [NodeType](Systems.Bpm.ProcessNodes.md#nodetype) | Type of the node. A=Text Annotation; E=Event; G=Gateway; T=Task; P=Sub-Process. [Required] [Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Process](Systems.Bpm.ProcessNodes.md#process) | [Processes](Systems.Bpm.Processes.md) | The process, to which this Node belongs. [Required] [Filter(multi eq)] [Owner] |
| [ProcessLane](Systems.Bpm.ProcessNodes.md#processlane) | [ProcessLanes](Systems.Bpm.ProcessLanes.md) | The process lane to which this Node belongs. [Required] [Filter(multi eq)] |


## Attribute Details

### Code

> Node code, unique within the process. Used as ID for XML serialization purposes. [Required] [Filter(eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### InstructionsHtml

> Detailed instructions to the executor in HTML format. [Filter(eq;like)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Name

> Multilanguage process name. [Required] [Filter(eq;like)]

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### NodeType

> Type of the node. A=Text Annotation; E=Event; G=Gateway; T=Task; P=Sub-Process. [Required] [Filter(eq;like)]

_Type_: **[NodeType](Systems.Bpm.ProcessNodes.md#nodetype)**  
Allowed values for the [NodeType](Systems.Bpm.ProcessNodes.md#nodetype) data attribute  
_Allowed Values (Systems.Bpm.ProcessNodesRepository.NodeType Enum Members)_  

| Value | Description |
| ---- | --- |
| Activity | Activity value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Activity' |
| Event | Event value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Event' |
| Gateway | Gateway value. Stored as 'G'. <br /> _Database Value:_ 'G' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Gateway' |
| Artifact | Artifact value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Artifact' |

_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


## Reference Details

### Process

> The process, to which this Node belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Processes](Systems.Bpm.Processes.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### ProcessLane

> The process lane to which this Node belongs. [Required] [Filter(multi eq)]

_Type_: **[ProcessLanes](Systems.Bpm.ProcessLanes.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.ProcessNodes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Bpm.ProcessNodes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_ProcessNodes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_ProcessNodes?$top=10>

