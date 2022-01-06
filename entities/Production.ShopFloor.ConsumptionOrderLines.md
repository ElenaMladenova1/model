---
uid: Production.ShopFloor.ConsumptionOrderLines
---
# Production.ShopFloor.ConsumptionOrderLines Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

Detail lines of orders for material consumption. Entity: Prd_Consumption_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineOrd}. {ConsumptionOrder.DocumentNo} {ConsumptionOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_ConsumptionOrder.DocumentNo_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  
Aggregate Root:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantity](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Requested quantity of the material. `Unit: ConsumedQuantityUnit` `Required` `Filter(ge;le)` 
| [ConsumedQuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The requested quantity equivalence in the base measurement category of the requested material. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [ConsumedStandard<br />QuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient). `Required` `Filter(eq)` `ReadOnly` 
| [Id](Production.ShopFloor.ConsumptionOrderLines.md#id) | guid |  
| [LineOrd](Production.ShopFloor.ConsumptionOrderLines.md#lineord) | int32 | Non-unique line number within the order. `Required` 
| [Notes](Production.ShopFloor.ConsumptionOrderLines.md#notes) | string (max) __nullable__ | Notes for this ConsumptionOrderLine. 
| [ObjectVersion](Production.ShopFloor.ConsumptionOrderLines.md#objectversion) | int32 |  
| [ScheduledDateTime](Production.ShopFloor.ConsumptionOrderLines.md#scheduleddatetime) | datetime __nullable__ | The scheduled date, when the material is needed. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantityUnit](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantityunit) | [MeasurementUnits](General.MeasurementUnits.md) | Measurement unit of the requested quantity. `Required` `Filter(multi eq)` |
| [ConsumptionOrder](Production.ShopFloor.ConsumptionOrderLines.md#consumptionorder) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Production.ShopFloor.ConsumptionOrderLines.md#document) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.ConsumptionOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If not null, specifies that the material has to be consumed from specific lot. `Filter(multi eq)` |
| [Product](Production.ShopFloor.ConsumptionOrderLines.md#product) | [Products](General.Products.Products.md) | The requested material. `Required` `Filter(multi eq)` |
| [SerialNumber](Production.ShopFloor.ConsumptionOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not null, specifies that the material has to be consumed with specific serial number. `Filter(multi eq)` |
| [Store](Production.ShopFloor.ConsumptionOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store, from which the material is requested. `Filter(multi eq)` |
| [StoreBin](Production.ShopFloor.ConsumptionOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | If not null, specifies that the material has to be consumed from specific store bin. `Filter(multi eq)` |
| [WorkOrderItemIngredient](Production.ShopFloor.ConsumptionOrderLines.md#workorderitemingredient) | [WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md) | The Work Order Item Ingredient for which we are ordering materials. `Required` `Filter(multi eq)` |


## Attribute Details

### ConsumedQuantity

Requested quantity of the material. `Unit: ConsumedQuantityUnit` `Required` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ConsumedQuantityUnit == null), null, IIF( ( obj.WorkOrderItemIngredient != null), obj.WorkOrderItemIngredient.GetSumConsumedQuantity( obj.ConsumedQuantityUnit), obj.ConsumedQuantity))`
### ConsumedQuantityBase

The requested quantity equivalence in the base measurement category of the requested material. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumptionType

Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient). `Required` `Filter(eq)` `ReadOnly`

_Type_: **[ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype)**  
Allowed values for the `ConsumptionType`(Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) data attribute  
_Allowed Values (Production.ShopFloor.ConsumptionOrderLinesRepository.ConsumptionType Enum Members)_  

| Value | Description |
| ---- | --- |
| ForSpecifiedItem | ForSpecifiedItem value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ForSpecifiedItem' |
| ForAllItems | ForAllItems value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ForAllItems' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.WorkOrderItemIngredient != null) AndAlso ( obj.WorkOrderItemIngredient.WorkOrderItem != null)), ForSpecifiedItem, ForAllItems)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineOrd

Non-unique line number within the order. `Required`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ConsumptionOrderLine.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ScheduledDateTime

The scheduled date, when the material is needed. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  


## Reference Details

### ConsumedQuantityUnit

Measurement unit of the requested quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### ConsumptionOrder

The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### Document

The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### Lot

If not null, specifies that the material has to be consumed from specific lot. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The requested material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.WorkOrderItemIngredient.Material`
### SerialNumber

If not null, specifies that the material has to be consumed with specific serial number. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Store

The store, from which the material is requested. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

_Back-End Default Expression:_  
`obj.ConsumptionOrder.Store`

_Front-End Recalc Expressions:_  
`obj.ConsumptionOrder.Store`
### StoreBin

If not null, specifies that the material has to be consumed from specific store bin. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### WorkOrderItemIngredient

The Work Order Item Ingredient for which we are ordering materials. `Required` `Filter(multi eq)`

_Type_: **[WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Production_ShopFloor_ConsumptionOrderLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_ConsumptionOrderLines?$top=10>

