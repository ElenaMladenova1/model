# Projects.ProjectTaskMaterials

Contains the materials, which are required for a project task. Entity: Prj_Project_Task_Materials

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.ProjectTaskMaterials.md#Id) | guid |  
| [BudgetedMaterialAmount](Projects.ProjectTaskMaterials.md#BudgetedMaterialAmount) | [Amount](../data-types/Amount.md) (nullable) | Budgeted amount for the material in the currency of the project. null means there is still no budgeted amount. [Currency: ProjectTask.Project.BudgetingCurrency] 
| [LineNumber](Projects.ProjectTaskMaterials.md#LineNumber) | int32 | Line number within the task, increased in steps of 10. Used for sorting purposes. [Required] [Default(0)] 
| [Quantity](Projects.ProjectTaskMaterials.md#Quantity) | [Quantity](../data-types/Quantity.md) | The required quantity of the material. [Unit: QuantityUnit] [Required] [Default(1)] 
| [QuantityBase](Projects.ProjectTaskMaterials.md#QuantityBase) | decimal | The equivalence of Quantity in the base measurement unit of the Material. [Required] [Default(0)] [ReadOnly] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaterialProduct](Projects.ProjectTaskMaterials.md#MaterialProduct) | [General.Products.Products](General.Products.Products.md) | The product Id of the required material. [Required] [Filter(multi eq)] |
| [ProjectTask](Projects.ProjectTaskMaterials.md#ProjectTask) | [Projects.ProjectTasks](Projects.ProjectTasks.md) | The task for which is the material requirement. [Required] [Filter(multi eq)] [Owner] |
| [QuantityUnit](Projects.ProjectTaskMaterials.md#QuantityUnit) | [General.MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of the required quantity. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### BudgetedMaterialAmount

> Budgeted amount for the material in the currency of the project. null means there is still no budgeted amount. [Currency: ProjectTask.Project.BudgetingCurrency]

_Type_: **[Amount](../data-types/Amount.md) (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`IIF((obj.MaterialProduct != null), obj.CalculateBudgetMaterialAmount(obj.Quantity), new Amount(0, obj.ProjectTask.Project.BudgetingCurrency))`
### LineNumber

> Line number within the task, increased in steps of 10. Used for sorting purposes. [Required] [Default(0)]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

_Back-End Default Expression:_  
`(obj.ProjectTask.Materials.Select(c => c.LineNumber).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.ProjectTask.Materials.Select(c => c.LineNumber).DefaultIfEmpty(0).Max() + 10)`
### Quantity

> The required quantity of the material. [Unit: QuantityUnit] [Required] [Default(1)]

_Type_: **[Quantity](../data-types/Quantity.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### QuantityBase

> The equivalence of Quantity in the base measurement unit of the Material. [Required] [Default(0)] [ReadOnly]

_Type_: **decimal**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

_Front-End Recalc Expressions:_  
`IIF(((obj.QuantityUnit != null) AndAlso (obj.MaterialProduct != null)), obj.Quantity.ConvertTo(obj.MaterialProduct.BaseUnit, obj.MaterialProduct).Value, obj.QuantityBase)`

## Reference Details

### MaterialProduct

> The product Id of the required material. [Required] [Filter(multi eq)]

_Type_: **[General.Products.Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ProjectTask

> The task for which is the material requirement. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Projects.ProjectTasks](Projects.ProjectTasks.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### QuantityUnit

> The measurement unit of the required quantity. [Required] [Filter(multi eq)]

_Type_: **[General.MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Projects.ProjectTaskMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Projects.ProjectTaskMaterials erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Projects.ProjectTaskMaterials erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_ProjectTaskMaterials?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_ProjectTaskMaterials?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Prj_Project_Task_Materials?$top=10>
