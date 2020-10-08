# Logistics.Inventory.StoreTransactionLines

Details records of Transactions. Each detail contains the movement for one product. Entity: Inv_Transaction_Lines

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.StoreTransactionLines.md#Id) | guid |  
| [AllowOverExecution](Logistics.Inventory.StoreTransactionLines.md#AllowOverExecution) | boolean | When true, specifies, that we explicitly allow over-execution. Over-execution is when the quantity in all execution lines exceed the quantity in the parent store order line. [Required] [Default(false)] 
| [Finished](Logistics.Inventory.StoreTransactionLines.md#Finished) | boolean (nullable) | True if this transaction entry completes the operation. false if there might be more entries. [Default(false)] [Filter(eq)] 
| [GuaranteePeriodDays](Logistics.Inventory.StoreTransactionLines.md#GuaranteePeriodDays) | int32 (nullable) | Guarantee period in days for the offered product. null for non-serviced products. 
| [LineBaseCost](Logistics.Inventory.StoreTransactionLines.md#LineBaseCost) | [Amount](../data-types/Amount.md) | The cost of the transaction in the currency of the enterprise company. [Currency: TransactionObj.EnterpriseCompany.BaseCurrency] [Required] [Default(0)] 
| [LineCost](Logistics.Inventory.StoreTransactionLines.md#LineCost) | [Amount](../data-types/Amount.md) | Total cost for the line. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)] 
| [LineDocumentCost](Logistics.Inventory.StoreTransactionLines.md#LineDocumentCost) | [Amount](../data-types/Amount.md) | The cost of the transaction in the currency of the document. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)] [ReadOnly] 
| [LineNo](Logistics.Inventory.StoreTransactionLines.md#LineNo) | int32 | Line number, unique within the store transaction. [Required] 
| [LineProductCost](Logistics.Inventory.StoreTransactionLines.md#LineProductCost) | [Amount](../data-types/Amount.md) | The cost of the transaction in the currency of the product. [Currency: Product.CostingCurrency] [Required] [Default(0)] [ReadOnly] 
| [LineStoreCost](Logistics.Inventory.StoreTransactionLines.md#LineStoreCost) | [Amount](../data-types/Amount.md) | The cost of the transaction in the currency of the warehouse. [Currency: TransactionObj.Store.Currency] [Required] [Default(0)] [ReadOnly] 
| [Notes](Logistics.Inventory.StoreTransactionLines.md#Notes) | string (nullable) | Notes for this StoreTransactionLine. 
| [ParentLineId](Logistics.Inventory.StoreTransactionLines.md#ParentLineId) | guid (nullable) | Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. [Filter(multi eq)] 
| [ParentLineNo](Logistics.Inventory.StoreTransactionLines.md#ParentLineNo) | int32 (nullable) | The number of the line within the parent document, which the current line executes. null when the current line does not execute line. 
| [Quantity](Logistics.Inventory.StoreTransactionLines.md#Quantity) | [Quantity](../data-types/Quantity.md) | The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. null means that the quantity is specified only in base measurement unit. [Unit: QuantityUnit] [Required] [Default(0)] 
| [QuantityBase](Logistics.Inventory.StoreTransactionLines.md#QuantityBase) | [Quantity](../data-types/Quantity.md) | The quantity of the stock received/issued in base measurement unit. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [Filter(ge;le)] 
| [StandardQuantityBase](Logistics.Inventory.StoreTransactionLines.md#StandardQuantityBase) | [Quantity](../data-types/Quantity.md) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] (Introduced in version 18.2.100.0) 
| [TempOrderNo](Logistics.Inventory.StoreTransactionLines.md#TempOrderNo) | string (nullable) | Obsolete. Not used. [Filter(eq)] 
| [TransactionTimestamp](Logistics.Inventory.StoreTransactionLines.md#TransactionTimestamp) | datetime (nullable) | Exact time when the transaction changes the cost of the product. [Filter(ge;le)] [ORD] 
| [UnitCost](Logistics.Inventory.StoreTransactionLines.md#UnitCost) | [Amount](../data-types/Amount.md) | Cost for 1 of the specified quantity. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Lot](Logistics.Inventory.StoreTransactionLines.md#Lot) | [Logistics.Inventory.Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. [Filter(multi eq)] |
| [OriginalProduct](Logistics.Inventory.StoreTransactionLines.md#OriginalProduct) | [General.Products.Products](General.Products.Products.md) (nullable) | When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead. [Filter(multi eq)] |
| [ParentDocument](Logistics.Inventory.StoreTransactionLines.md#ParentDocument) | [General.Documents](General.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. [Filter(multi eq)] |
| [ParentStoreOrderLine](Logistics.Inventory.StoreTransactionLines.md#ParentStoreOrderLine) | [Logistics.Inventory.StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable) | The line, containing the ordered quantity, which this execution line executes. [Filter(multi eq)] |
| [ProductCode](Logistics.Inventory.StoreTransactionLines.md#ProductCode) | [General.Products.ProductCodes](General.Products.ProductCodes.md) (nullable) | Used to set the Product_Id thru the coding systems. [Filter(multi eq)] |
| [Product](Logistics.Inventory.StoreTransactionLines.md#Product) | [General.Products.Products](General.Products.Products.md) | The item that was received/issued. [Required] [Filter(multi eq)] |
| [ProductVariant](Logistics.Inventory.StoreTransactionLines.md#ProductVariant) | [General.ProductVariants](General.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. [Filter(multi eq)] |
| [QuantityUnit](Logistics.Inventory.StoreTransactionLines.md#QuantityUnit) | [General.MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of Quantity. null means that the quantity is specified only in base measurement unit. [Required] [Filter(multi eq)] |
| [SerialNumber](Logistics.Inventory.StoreTransactionLines.md#SerialNumber) | [Logistics.Inventory.SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serialized items. [Filter(multi eq)] |
| [StoreBin](Logistics.Inventory.StoreTransactionLines.md#StoreBin) | [Logistics.Inventory.StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. [Filter(multi eq)] |
| [TransactionObj](Logistics.Inventory.StoreTransactionLines.md#TransactionObj) | [Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. [Required] [Filter(multi eq)] [Owner] |
| [Document](Logistics.Inventory.StoreTransactionLines.md#Document) | [Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### AllowOverExecution

> When true, specifies, that we explicitly allow over-execution. Over-execution is when the quantity in all execution lines exceed the quantity in the parent store order line. [Required] [Default(false)]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Finished

> True if this transaction entry completes the operation. false if there might be more entries. [Default(false)] [Filter(eq)]

_Type_: **boolean (nullable)**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### GuaranteePeriodDays

> Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`obj.Product.GuaranteePeriodDays`
### LineBaseCost

> The cost of the transaction in the currency of the enterprise company. [Currency: TransactionObj.EnterpriseCompany.BaseCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineCost

> Total cost for the line. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineDocumentCost

> The cost of the transaction in the currency of the document. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)] [ReadOnly]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineNo

> Line number, unique within the store transaction. [Required]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`(obj.TransactionObj.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.TransactionObj.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`
### LineProductCost

> The cost of the transaction in the currency of the product. [Currency: Product.CostingCurrency] [Required] [Default(0)] [ReadOnly]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### LineStoreCost

> The cost of the transaction in the currency of the warehouse. [Currency: TransactionObj.Store.Currency] [Required] [Default(0)] [ReadOnly]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### Notes

> Notes for this StoreTransactionLine.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ParentLineId

> Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. [Filter(multi eq)]

_Type_: **guid (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ParentLineNo

> The number of the line within the parent document, which the current line executes. null when the current line does not execute line.

_Type_: **int32 (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Quantity

> The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. null means that the quantity is specified only in base measurement unit. [Unit: QuantityUnit] [Required] [Default(0)]

_Type_: **[Quantity](../data-types/Quantity.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### QuantityBase

> The quantity of the stock received/issued in base measurement unit. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [Filter(ge;le)]

_Type_: **[Quantity](../data-types/Quantity.md)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

_Back-End Default Expression:_  
`IIF((((obj.Quantity == null) OrElse (obj.QuantityUnit == null)) OrElse (obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo(obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF((((obj.Quantity == null) OrElse (obj.QuantityUnit == null)) OrElse (obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo(obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

> The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. [Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] (Introduced in version 18.2.100.0)

_Type_: **[Quantity](../data-types/Quantity.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF((((obj.Quantity == null) OrElse (obj.QuantityUnit == null)) OrElse (obj.Product == null)), obj.StandardQuantityBase, IIF(obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo(obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF((((obj.Quantity == null) OrElse (obj.QuantityUnit == null)) OrElse (obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo(obj.Product.BaseUnit, obj.Product))`
### TempOrderNo

> Obsolete. Not used. [Filter(eq)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### TransactionTimestamp

> Exact time when the transaction changes the cost of the product. [Filter(ge;le)] [ORD]

_Type_: **datetime (nullable)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  

### UnitCost

> Cost for 1 of the specified quantity. [Currency: TransactionObj.DocumentCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  


## Reference Details

### Lot

> If non-null, contains the specific lot to use for the movement. [Filter(multi eq)]

_Type_: **[Logistics.Inventory.Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### OriginalProduct

> When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead. [Filter(multi eq)]

_Type_: **[General.Products.Products](General.Products.Products.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`obj.Product`
### ParentDocument

> The document, which the current line executes. null when the current line does not execute another line. [Filter(multi eq)]

_Type_: **[General.Documents](General.Documents.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ParentStoreOrderLine

> The line, containing the ordered quantity, which this execution line executes. [Filter(multi eq)]

_Type_: **[Logistics.Inventory.StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ProductCode

> Used to set the Product_Id thru the coding systems. [Filter(multi eq)]

_Type_: **[General.Products.ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Product

> The item that was received/issued. [Required] [Filter(multi eq)]

_Type_: **[General.Products.Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`obj.OriginalProduct`
### ProductVariant

> If specified determines which product variant of the current product in this line is used. [Filter(multi eq)]

_Type_: **[General.ProductVariants](General.ProductVariants.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### QuantityUnit

> The measurement unit of Quantity. null means that the quantity is specified only in base measurement unit. [Required] [Filter(multi eq)]

_Type_: **[General.MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### SerialNumber

> Item serial number for serialized items. null for non-serialized items. [Filter(multi eq)]

_Type_: **[Logistics.Inventory.SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### StoreBin

> Store bin, from/to which the transaction was performed. [Filter(multi eq)]

_Type_: **[Logistics.Inventory.StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### TransactionObj

> The transaction to which the transaction line belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Document

> The transaction to which the transaction line belongs. [Required] [Filter(multi eq)]

_Type_: **[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreTransactionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreTransactionLines?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Inv_Transaction_Lines?$top=10>
