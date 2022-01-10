---
uid: Logistics.Inventory.StoreTransactionLines
---
# Logistics.Inventory.StoreTransactionLines Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Details records of Transactions. Each detail contains the movement for one product. Entity: Inv_Transaction_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {TransactionObj.DocumentNo} {TransactionObj.DocumentType.TypeName:T}_  
Default Search Members:  
_TransactionObj.DocumentNo_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  
Aggregate Root:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowOverExecution](Logistics.Inventory.StoreTransactionLines.md#allowoverexecution) | boolean | When true, specifies, that we explicitly allow over-execution. Over-execution is when the quantity in all execution lines exceed the quantity in the parent store order line. `Required` `Default(false)` 
| [DisplayText](Logistics.Inventory.StoreTransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Finished](Logistics.Inventory.StoreTransactionLines.md#finished) | boolean __nullable__ | True if this transaction entry completes the operation. false if there might be more entries. `Default(false)` `Filter(eq)` 
| [GuaranteePeriodDays](Logistics.Inventory.StoreTransactionLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [Id](Logistics.Inventory.StoreTransactionLines.md#id) | guid |  
| [LineBaseCost](Logistics.Inventory.StoreTransactionLines.md#linebasecost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the enterprise company. `Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [LineCost](Logistics.Inventory.StoreTransactionLines.md#linecost) | [Amount (14, 2)](../data-types.md#amount) | Total cost for the line. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` 
| [LineDocumentCost](Logistics.Inventory.StoreTransactionLines.md#linedocumentcost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the document. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` `ReadOnly` 
| [LineNo](Logistics.Inventory.StoreTransactionLines.md#lineno) | int32 | Line number, unique within the store transaction. `Required` 
| [LineProductCost](Logistics.Inventory.StoreTransactionLines.md#lineproductcost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the product. `Currency: Product.CostingCurrency` `Required` `Default(0)` `ReadOnly` 
| [LineStoreCost](Logistics.Inventory.StoreTransactionLines.md#linestorecost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the warehouse. `Currency: TransactionObj.Store.Currency` `Required` `Default(0)` `ReadOnly` 
| [Notes](Logistics.Inventory.StoreTransactionLines.md#notes) | string (254) __nullable__ | Notes for this StoreTransactionLine. 
| [ObjectVersion](Logistics.Inventory.StoreTransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineId](Logistics.Inventory.StoreTransactionLines.md#parentlineid) | guid __nullable__ | Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. `Filter(multi eq)` 
| [ParentLineNo](Logistics.Inventory.StoreTransactionLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute line. 
| [Quantity](Logistics.Inventory.StoreTransactionLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. null means that the quantity is specified only in base measurement unit. `Unit: QuantityUnit` `Required` `Default(0)` 
| [QuantityBase](Logistics.Inventory.StoreTransactionLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)` 
| [StandardQuantityBase](Logistics.Inventory.StoreTransactionLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [TempOrderNo](Logistics.Inventory.StoreTransactionLines.md#temporderno) | string (50) __nullable__ | Obsolete. Not used. `Filter(eq)` 
| [TransactionTimestamp](Logistics.Inventory.StoreTransactionLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction changes the cost of the product. `Filter(ge;le)` `ORD` 
| [UnitCost](Logistics.Inventory.StoreTransactionLines.md#unitcost) | [Amount (14, 5)](../data-types.md#amount) | Cost for 1 of the specified quantity. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.StoreTransactionLines.md#document) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.StoreTransactionLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` |
| [OriginalProduct](Logistics.Inventory.StoreTransactionLines.md#originalproduct) | [Products](General.Products.Products.md) (nullable) | When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead. `Filter(multi eq)` |
| [ParentDocument](Logistics.Inventory.StoreTransactionLines.md#parentdocument) | [Documents](General.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [ParentStoreOrderLine](Logistics.Inventory.StoreTransactionLines.md#parentstoreorderline) | [StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable) | The line, containing the ordered quantity, which this execution line executes. `Filter(multi eq)` |
| [Product](Logistics.Inventory.StoreTransactionLines.md#product) | [Products](General.Products.Products.md) | The item that was received/issued. `Required` `Filter(multi eq)` |
| [ProductCode](Logistics.Inventory.StoreTransactionLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Used to set the Product_Id thru the coding systems. `Filter(multi eq)` |
| [ProductVariant](Logistics.Inventory.StoreTransactionLines.md#productvariant) | [ProductVariants](General.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` |
| [QuantityUnit](Logistics.Inventory.StoreTransactionLines.md#quantityunit) | [MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of Quantity. null means that the quantity is specified only in base measurement unit. `Required` `Filter(multi eq)` |
| [SerialNumber](Logistics.Inventory.StoreTransactionLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` |
| [StoreBin](Logistics.Inventory.StoreTransactionLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. `Filter(multi eq)` |
| [TransactionObj](Logistics.Inventory.StoreTransactionLines.md#transactionobj) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### AllowOverExecution

When true, specifies, that we explicitly allow over-execution. Over-execution is when the quantity in all execution lines exceed the quantity in the parent store order line. `Required` `Default(false)`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Finished

True if this transaction entry completes the operation. false if there might be more entries. `Default(false)` `Filter(eq)`

_Type_: **boolean __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`obj.Product.GuaranteePeriodDays`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineBaseCost

The cost of the transaction in the currency of the enterprise company. `Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineCost

Total cost for the line. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineDocumentCost

The cost of the transaction in the currency of the document. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` `ReadOnly`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineNo

Line number, unique within the store transaction. `Required`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.TransactionObj.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.TransactionObj.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineProductCost

The cost of the transaction in the currency of the product. `Currency: Product.CostingCurrency` `Required` `Default(0)` `ReadOnly`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineStoreCost

The cost of the transaction in the currency of the warehouse. `Currency: TransactionObj.Store.Currency` `Required` `Default(0)` `ReadOnly`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### Notes

Notes for this StoreTransactionLine.

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ParentLineId

Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute line.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Quantity

The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. null means that the quantity is specified only in base measurement unit. `Unit: QuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TempOrderNo

Obsolete. Not used. `Filter(eq)`

_Type_: **string (50) __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  

### TransactionTimestamp

Exact time when the transaction changes the cost of the product. `Filter(ge;le)` `ORD`

_Type_: **datetime __nullable__**  
_Indexed_: **True**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  

### UnitCost

Cost for 1 of the specified quantity. `Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 5)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  


## Reference Details

### Document

The transaction to which the transaction line belongs. `Required` `Filter(multi eq)`

_Type_: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### OriginalProduct

When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.Product`
### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### ParentStoreOrderLine

The line, containing the ordered quantity, which this execution line executes. `Filter(multi eq)`

_Type_: **[StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The item that was received/issued. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.OriginalProduct`
### ProductCode

Used to set the Product_Id thru the coding systems. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)`

_Type_: **[ProductVariants](General.ProductVariants.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### QuantityUnit

The measurement unit of Quantity. null means that the quantity is specified only in base measurement unit. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### SerialNumber

Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### StoreBin

Store bin, from/to which the transaction was performed. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### TransactionObj

The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


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

[!list limit=1000 erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreTransactionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreTransactionLines?$top=10>

