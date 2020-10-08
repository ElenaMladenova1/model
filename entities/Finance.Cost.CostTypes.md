# Finance.Cost.CostTypes

Types of costs. Entity: Cost_Types

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Cost.CostTypes.md#Id) | guid |  
| [Code](Finance.Cost.CostTypes.md#Code) | string | Unique cost type code. Used for charting. [Required] [Filter(eq)] [ORD] 
| [Name](Finance.Cost.CostTypes.md#Name) | string | Multilanguage cost type name. [Required] [Filter(like)] 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Code

> Unique cost type code. Used for charting. [Required] [Filter(eq)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals**  
_Supports Order By_: **True**  

### Name

> Multilanguage cost type name. [Required] [Filter(like)]

_Type_: **string**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Finance.Cost.CostTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Cost.CostTypes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Finance.Cost.CostTypes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_CostTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_CostTypes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Cost_Types?$top=10>
