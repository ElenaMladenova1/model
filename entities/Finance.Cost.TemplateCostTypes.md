---
uid: Finance.Cost.TemplateCostTypes
---
# Finance.Cost.TemplateCostTypes Entity

**Namespace:** [Finance.Cost](Finance.Cost.md)  

Contains the cost types and their hierachy positions within a cost calculation. Entity: Cost_Template_Cost_Types

## Default Visualization
Default Display Text Format:  
_{CostTemplate.CostTemplateName}_  
Default Search Members:  
_CostTemplate.CostTemplateName_  
Name Data Member:  
_CostTemplate.CostTemplateName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Templates](Finance.Cost.Templates.md)  
Aggregate Root:  
[Finance.Cost.Templates](Finance.Cost.Templates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Finance.Cost.TemplateCostTypes.md#displaytext) | string |  
| [HierarchyLevel](Finance.Cost.TemplateCostTypes.md#hierarchylevel) | int32 | The level in the hierarchy on which this cost is incurred (0..9). `Required` `Filter(ge;le)` 
| [Id](Finance.Cost.TemplateCostTypes.md#id) | guid |  
| [ObjectVersion](Finance.Cost.TemplateCostTypes.md#objectversion) | int32 |  

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostTemplate](Finance.Cost.TemplateCostTypes.md#costtemplate) | [Templates](Finance.Cost.Templates.md) | The <see cref="Template"/> to which this TemplateCostType belongs. `Required` `Filter(multi eq)` `Owner` |
| [CostType](Finance.Cost.TemplateCostTypes.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The Cost Type for which the hierarchy is specified. `Required` `Filter(multi eq)` |


## Attribute Details

### DisplayText

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### HierarchyLevel

The level in the hierarchy on which this cost is incurred (0..9). `Required` `Filter(ge;le)`

_Type_: **int32**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### CostTemplate

The <see cref="Template"/> to which this TemplateCostType belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Templates](Finance.Cost.Templates.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### CostType

The Cost Type for which the hierarchy is specified. `Required` `Filter(multi eq)`

_Type_: **[CostTypes](Finance.Cost.CostTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  



## Business Rules

[!list limit=1000 erp.entity=Finance.Cost.TemplateCostTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.TemplateCostTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_TemplateCostTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_TemplateCostTypes?$top=10>

