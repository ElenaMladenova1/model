---
uid: Finance.Cost.DistributionResults
---
# Finance.Cost.DistributionResults Entity

**Namespace:** [Finance.Cost](Finance.Cost.md)  

Contains the results of a cost distribution calculation. Entity: Cost_Distribution_Results

## Default Visualization
Default Display Text Format:  
_{CostDistribution.EntityName}_  
Default Search Members:  
_CostDistribution.EntityName_  
Name Data Member:  
_CostDistribution.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Distributions](Finance.Cost.Distributions.md)  
Aggregate Root:  
[Finance.Cost.Distributions](Finance.Cost.Distributions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Finance.Cost.DistributionResults.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DistributedAmountBase](Finance.Cost.DistributionResults.md#distributedamountbase) | [Amount (14, 5)](../data-types.md#amount) | The amount (in base currency) of the distributed cost. The amount is calculated for the combination of output and cost type. `Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required` 
| [Id](Finance.Cost.DistributionResults.md#id) | guid |  
| [LineNo](Finance.Cost.DistributionResults.md#lineno) | int32 | Consecutive line number (within the cost distribution document) of the result. `Required` 
| [ObjectVersion](Finance.Cost.DistributionResults.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OutputLineNo](Finance.Cost.DistributionResults.md#outputlineno) | int32 | The line number (within the document) of the output over which the cost is distributed. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostDistribution](Finance.Cost.DistributionResults.md#costdistribution) | [Distributions](Finance.Cost.Distributions.md) | The <see cref="Distribution"/> to which this DistributionResult belongs. `Required` `Filter(multi eq)` `Owner` |
| [CostType](Finance.Cost.DistributionResults.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The cost type for which the current distribution is calculated. `Required` `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### DistributedAmountBase

The amount (in base currency) of the distributed cost. The amount is calculated for the combination of output and cost type. `Currency: CostDistribution.EnterpriseCompany.BaseCurrency` `Required`

_Type_: **[Amount (14, 5)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineNo

Consecutive line number (within the cost distribution document) of the result. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.CostDistribution.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.CostDistribution.Results.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### OutputLineNo

The line number (within the document) of the output over which the cost is distributed. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### CostDistribution

The <see cref="Distribution"/> to which this DistributionResult belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Distributions](Finance.Cost.Distributions.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### CostType

The cost type for which the current distribution is calculated. `Required` `Filter(multi eq)`

_Type_: **[CostTypes](Finance.Cost.CostTypes.md)**  
_Category_: **System**  
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

[!list limit=1000 erp.entity=Finance.Cost.DistributionResults erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.DistributionResults erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_DistributionResults?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_DistributionResults?$top=10>

