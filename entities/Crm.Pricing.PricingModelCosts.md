# Crm.Pricing.PricingModelCosts

List of costs, associated with a pricing model. Entity: Crm_Pricing_Model_Costs

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PricingModelCosts.md#Id) | guid |  
| [AmountPerUnit](Crm.Pricing.PricingModelCosts.md#AmountPerUnit) | [Amount](../data-types/Amount.md) (nullable) | Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement_Unit_Id. null when the cost is calculated in a different way. [Currency: PricingModel.Currency] 
| [AmountPercent](Crm.Pricing.PricingModelCosts.md#AmountPercent) | decimal (nullable) | Used when the cost is calculated as percent of the amount. null when the cost is calculated in a different way. 
| [LineNo](Crm.Pricing.PricingModelCosts.md#LineNo) | int32 | The consequtive number of the cost within the pricing model. [Required] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostType](Crm.Pricing.PricingModelCosts.md#CostType) | [Finance.Cost.CostTypes](Finance.Cost.CostTypes.md) | The cost type, which is listed for the pricing model. [Required] [Filter(multi eq)] |
| [MeasurementUnit](Crm.Pricing.PricingModelCosts.md#MeasurementUnit) | [General.MeasurementUnits](General.MeasurementUnits.md) (nullable) | The measurement unit for which the Amount_Per_Unit is defined. null when the cost is calculated in a different way. [Filter(multi eq)] |
| [PricingModel](Crm.Pricing.PricingModelCosts.md#PricingModel) | [Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md) | Pricing model, for which the cost is defined. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### AmountPerUnit

> Used when the cost is calculated as amount per unit of the product. The unit is defined in Measurement_Unit_Id. null when the cost is calculated in a different way. [Currency: PricingModel.Currency]

_Type_: **[Amount](../data-types/Amount.md) (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### AmountPercent

> Used when the cost is calculated as percent of the amount. null when the cost is calculated in a different way.

_Type_: **decimal (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### LineNo

> The consequtive number of the cost within the pricing model. [Required]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`(obj.PricingModel.Costs.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.PricingModel.Costs.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`

## Reference Details

### CostType

> The cost type, which is listed for the pricing model. [Required] [Filter(multi eq)]

_Type_: **[Finance.Cost.CostTypes](Finance.Cost.CostTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### MeasurementUnit

> The measurement unit for which the Amount_Per_Unit is defined. null when the cost is calculated in a different way. [Filter(multi eq)]

_Type_: **[General.MeasurementUnits](General.MeasurementUnits.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### PricingModel

> Pricing model, for which the cost is defined. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Crm.Pricing.PricingModelCosts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Crm.Pricing.PricingModelCosts erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Crm.Pricing.PricingModelCosts erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Pricing_PricingModelCosts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PricingModelCosts?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Pricing_Model_Costs?$top=10>
