# Finance.Assets.DepreciationPlanLines

Each record contains one depreciation plan for one valuation model of one asset. Entity: Ast_Depreciation_Plan_Lines

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.DepreciationPlanLines.md#Id) | guid |  
| [DepreciationEndDate](Finance.Assets.DepreciationPlanLines.md#DepreciationEndDate) | datetime | End date of the depreciation plan for this asset. [Required] 
| [DepreciationStartDate](Finance.Assets.DepreciationPlanLines.md#DepreciationStartDate) | datetime | Start date of the depreciation plan for this asset. [Required] 
| [LineNo](Finance.Assets.DepreciationPlanLines.md#LineNo) | int32 | Consecutive number of the line within the depreciation plan. [Required] [Filter(eq)] 
| [PlanDepreciationValue](Finance.Assets.DepreciationPlanLines.md#PlanDepreciationValue) | [Amount](../data-types/Amount.md) | The part of the total amount of the asset (in the currency of the asset), which is due for depreciation. [Currency: Asset.ValuationCurrency] [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Asset](Finance.Assets.DepreciationPlanLines.md#Asset) | [Finance.Assets.Assets](Finance.Assets.Assets.md) | The asset that is planned for depreciation. [Required] [Filter(multi eq)] |
| [DepreciationMethod](Finance.Assets.DepreciationPlanLines.md#DepreciationMethod) | [Finance.Assets.DepreciationMethods](Finance.Assets.DepreciationMethods.md) | Depreciation method by which the asset will be depreciated. [Required] [Filter(multi eq)] |
| [DepreciationPlan](Finance.Assets.DepreciationPlanLines.md#DepreciationPlan) | [Finance.Assets.DepreciationPlans](Finance.Assets.DepreciationPlans.md) | The [DepreciationPlan](Finance.Assets.DepreciationPlanLines.md#DepreciationPlan) to which this DepreciationPlanLine belongs. [Required] [Filter(multi eq)] [Owner] |
| [ValuationModel](Finance.Assets.DepreciationPlanLines.md#ValuationModel) | [Finance.Assets.ValuationModels](Finance.Assets.ValuationModels.md) | Valuation model in which the asset is accounted. [Required] [Filter(multi eq)] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| FixedValues | [Finance.Assets.DepreciationPlanLineFixedValues](Finance.Assets.DepreciationPlanLineFixedValues.md) | List of [DepreciationPlanLineFixedValue](Finance.Assets.DepreciationPlanLineFixedValues.md) child objects, based on the [Finance.Assets.DepreciationPlanLineFixedValue.DepreciationPlanLine](Finance.Assets.DepreciationPlanLineFixedValues.md#DepreciationPlanLine) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### DepreciationEndDate

> End date of the depreciation plan for this asset. [Required]

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### DepreciationStartDate

> Start date of the depreciation plan for this asset. [Required]

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### LineNo

> Consecutive number of the line within the depreciation plan. [Required] [Filter(eq)]

_Type_: **int32**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`(obj.DepreciationPlan.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.DepreciationPlan.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`
### PlanDepreciationValue

> The part of the total amount of the asset (in the currency of the asset), which is due for depreciation. [Currency: Asset.ValuationCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  


## Reference Details

### Asset

> The asset that is planned for depreciation. [Required] [Filter(multi eq)]

_Type_: **[Finance.Assets.Assets](Finance.Assets.Assets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### DepreciationMethod

> Depreciation method by which the asset will be depreciated. [Required] [Filter(multi eq)]

_Type_: **[Finance.Assets.DepreciationMethods](Finance.Assets.DepreciationMethods.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### DepreciationPlan

> The [DepreciationPlan](Finance.Assets.DepreciationPlanLines.md#DepreciationPlan) to which this DepreciationPlanLine belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Finance.Assets.DepreciationPlans](Finance.Assets.DepreciationPlans.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ValuationModel

> Valuation model in which the asset is accounted. [Required] [Filter(multi eq)]

_Type_: **[Finance.Assets.ValuationModels](Finance.Assets.ValuationModels.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Finance.Assets.DepreciationPlanLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Assets.DepreciationPlanLines erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Finance.Assets.DepreciationPlanLines erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Assets_DepreciationPlanLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Assets_DepreciationPlanLines?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Ast_Depreciation_Plan_Lines?$top=10>
