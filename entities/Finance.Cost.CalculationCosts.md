---
uid: Finance.Cost.CalculationCosts
---
# Finance.Cost.CalculationCosts Entity

**Namespace:** [Finance.Cost](Finance.Cost.md)  

Contains the calculated costs allocated to the different Cost Types. Entity: Cost_Calculation_Costs

## Default Visualization
Default Display Text Format:  
_{Calculation.EntityName}_  
Default Search Members:  
_Calculation.EntityName_  
Name Data Member:  
_Calculation.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  
Aggregate Root:  
[Finance.Cost.Calculations](Finance.Cost.Calculations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Finance.Cost.CalculationCosts.md#amount) | decimal (14, 2) | The allocated amount of costs in the currency of the calculation. `Required` `Default(0)` 
| [DisplayText](Finance.Cost.CalculationCosts.md#displaytext) | string |  
| [Id](Finance.Cost.CalculationCosts.md#id) | guid |  
| [LineNo](Finance.Cost.CalculationCosts.md#lineno) | int32 | Consecutive number of the line within the calculation. `Required` 
| [ObjectVersion](Finance.Cost.CalculationCosts.md#objectversion) | int32 |  
| [ProjectId](Finance.Cost.CalculationCosts.md#projectid) | guid __nullable__ | The Project, which absorbed the cost. `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Calculation](Finance.Cost.CalculationCosts.md#calculation) | [Calculations](Finance.Cost.Calculations.md) | The <see cref="Calculation"/> to which this CalculationCost belongs. `Required` `Filter(multi eq)` `Owner` |
| [CostCenter](Finance.Cost.CalculationCosts.md#costcenter) | [CostCenters](Finance.Accounting.CostCenters.md) (nullable) | The Cost Center, which absorbed the cost. `Filter(multi eq)` |
| [CostType](Finance.Cost.CalculationCosts.md#costtype) | [CostTypes](Finance.Cost.CostTypes.md) | The Cost Type, which absorbed the cost. `Required` `Filter(multi eq)` |
| [Lot](Finance.Cost.CalculationCosts.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Lot, which absorbed the cost. `Filter(multi eq)` |
| [Product](Finance.Cost.CalculationCosts.md#product) | [Products](General.Products.Products.md) (nullable) | The Product, which absorbed the cost. `Filter(multi eq)` |
| [SalesOrder](Finance.Cost.CalculationCosts.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | The Sales Order, which absorbed the cost. `Filter(multi eq)` |
| [Workgroup](Finance.Cost.CalculationCosts.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) (nullable) | The Workgroup, which absorbed the cost. `Filter(multi eq)` |


## Attribute Details

### Amount

The allocated amount of costs in the currency of the calculation. `Required` `Default(0)`

_Type_: **decimal (14, 2)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### DisplayText

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineNo

Consecutive number of the line within the calculation. `Required`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.Calculation.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Calculation.Costs.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ProjectId

The Project, which absorbed the cost. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Supported Filters_: **Equals, EqualsIn**  


## Reference Details

### Calculation

The <see cref="Calculation"/> to which this CalculationCost belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Calculations](Finance.Cost.Calculations.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### CostCenter

The Cost Center, which absorbed the cost. `Filter(multi eq)`

_Type_: **[CostCenters](Finance.Accounting.CostCenters.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### CostType

The Cost Type, which absorbed the cost. `Required` `Filter(multi eq)`

_Type_: **[CostTypes](Finance.Cost.CostTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### Lot

The Lot, which absorbed the cost. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The Product, which absorbed the cost. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### SalesOrder

The Sales Order, which absorbed the cost. `Filter(multi eq)`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Workgroup

The Workgroup, which absorbed the cost. `Filter(multi eq)`

_Type_: **[Workgroups](Production.Resources.Workgroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Cost.CalculationCosts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Cost.CalculationCosts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Cost_CalculationCosts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Cost_CalculationCosts?$top=10>

