# Projects.TaskTypes

Represents the different types of tasks, which can be included in the projects. Entity: Prj_Task_Types

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.TaskTypes.md#Id) | guid |  
| [Description](Projects.TaskTypes.md#Description) | [MultilanguageString](../data-types/MultilanguageString.md) (nullable) | Multilanguage description of the task type. 
| [DisplayOrder](Projects.TaskTypes.md#DisplayOrder) | int32 | Display order position of the task. Lowest numbers are shown first (on top). [Required] [Default(1)] 
| [Icon](Projects.TaskTypes.md#Icon) | byte[] (nullable) | Icon representing the task type. Preferrably 32x32 pixels. 
| [Name](Projects.TaskTypes.md#Name) | [MultilanguageString](../data-types/MultilanguageString.md) | The multilanguage task type name. [Required] [Filter(multi eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectType](Projects.TaskTypes.md#ProjectType) | [Projects.ProjectTypes](Projects.ProjectTypes.md) (nullable) | When not null, specifies that this task type can be used only for projects of the specified type. [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Description

> Multilanguage description of the task type.

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md) (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### DisplayOrder

> Display order position of the task. Lowest numbers are shown first (on top). [Required] [Default(1)]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  

### Icon

> Icon representing the task type. Preferrably 32x32 pixels.

_Type_: **byte[] (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Name

> The multilanguage task type name. [Required] [Filter(multi eq;like)]

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md)**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  


## Reference Details

### ProjectType

> When not null, specifies that this task type can be used only for projects of the specified type. [Filter(multi eq)]

_Type_: **[Projects.ProjectTypes](Projects.ProjectTypes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Projects.TaskTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Projects.TaskTypes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Projects.TaskTypes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TaskTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TaskTypes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Prj_Task_Types?$top=10>
