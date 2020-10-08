# Finance.Cost.TemplateCostTypes

Contains the cost types and their hierachy positions within a cost calculation. Entity: Cost_Template_Cost_Types

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Cost.TemplateCostTypes.md#Id) | guid |  
| [HierarchyLevel](Finance.Cost.TemplateCostTypes.md#HierarchyLevel) | int32 | The level in the hierarchy on which this cost is incurred (0..9). [Required] [Filter(ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostTemplate](Finance.Cost.TemplateCostTypes.md#CostTemplate) | [Finance.Cost.Templates](Finance.Cost.Templates.md) | The [Template](Finance.Cost.Templates.md) to which this TemplateCostType belongs. [Required] [Filter(multi eq)] [Owner] |
| [CostType](Finance.Cost.TemplateCostTypes.md#CostType) | [Finance.Cost.CostTypes](Finance.Cost.CostTypes.md) | The Cost Type for which the hierarchy is specified. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### HierarchyLevel

> The level in the hierarchy on which this cost is incurred (0..9). [Required] [Filter(ge;le)]

_Type_: **int32**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  


## Reference Details

### CostTemplate

> The [Template](Finance.Cost.Templates.md) to which this TemplateCostType belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Finance.Cost.Templates](Finance.Cost.Templates.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### CostType

> The Cost Type for which the hierarchy is specified. [Required] [Filter(multi eq)]

_Type_: **[Finance.Cost.CostTypes](Finance.Cost.CostTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Finance.Cost.TemplateCostTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Cost.TemplateCostTypes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Finance.Cost.TemplateCostTypes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_TemplateCostTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_TemplateCostTypes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Cost_Template_Cost_Types?$top=10>
