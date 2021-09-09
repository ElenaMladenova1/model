---
uid: Logistics.Shipment.ShipmentLines
---
# Logistics.Shipment.ShipmentLines Entity

**Namespace:** [Logistics.Shipment](Logistics.Shipment.md)  

Represents detail lines of shipments. Each line contains the shipment of one product. Entity: Log_Shipment_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo} : {Shipment.DocumentNo} {Shipment.DocumentType.TypeName:T}_  
Default Search Member:  
_Shipment.DocumentNo_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  
Aggregate Root:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxCount](Logistics.Shipment.ShipmentLines.md#boxcount) | int32 __nullable__ | The count of boxes in which the goods are packaged. null means unknown. 
| [Finished](Logistics.Shipment.ShipmentLines.md#finished) | boolean | True if this shipment should prohibit further shipments for the sales order line. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [GrossWeightkg](Logistics.Shipment.ShipmentLines.md#grossweightkg) | decimal (12, 3) __nullable__ | The gross weight of the whole line in kilogramms. null means unknown. 
| [GuaranteePeriodDays](Logistics.Shipment.ShipmentLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [Heightm](Logistics.Shipment.ShipmentLines.md#heightm) | decimal (12, 3) __nullable__ | The height of the package in meters. null means unknown. 
| [Id](Logistics.Shipment.ShipmentLines.md#id) | guid |  
| [Lengthm](Logistics.Shipment.ShipmentLines.md#lengthm) | decimal (12, 3) __nullable__ | The length of the package in meters. null means unknown. 
| [LineNo](Logistics.Shipment.ShipmentLines.md#lineno) | int32 | Line number, unique for the shipment. `Required` 
| [LineRequiredDeliveryDate](Logistics.Shipment.ShipmentLines.md#linerequireddeliverydate) | datetime __nullable__ | Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly. 
| [NetWeightkg](Logistics.Shipment.ShipmentLines.md#netweightkg) | decimal (12, 3) __nullable__ | The net weight of the entire batch of goods in kilograms. null means unknown. 
| [Notes](Logistics.Shipment.ShipmentLines.md#notes) | string (max) __nullable__ | Specific notes for this line. 
| [PalletNo](Logistics.Shipment.ShipmentLines.md#palletno) | int32 __nullable__ | The number of the pallet in which the goods are packaged. null means unknown. 
| [ParentLineNo](Logistics.Shipment.ShipmentLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(multi eq)` 
| [Quantity](Logistics.Shipment.ShipmentLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity to be shipped. `Unit: QuantityUnit` `Required` 
| [QuantityBase](Logistics.Shipment.ShipmentLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [StandardQuantityBase](Logistics.Shipment.ShipmentLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [Volumel](Logistics.Shipment.ShipmentLines.md#volumel) | decimal (12, 3) __nullable__ | The volume in litres of the whole batch. null means unknown. 
| [Widthm](Logistics.Shipment.ShipmentLines.md#widthm) | decimal (12, 3) __nullable__ | The width of the package in meters. null means unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Shipment.ShipmentLines.md#document) | [Shipments](Logistics.Shipment.Shipments.md) | The `Shipment`(Logistics.Shipment.ShipmentLines.md#shipment) to which this ShipmentLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Shipment.ShipmentLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The store lot from which to take the goods. `Filter(multi eq)` |
| [ParentDocument](Logistics.Shipment.ShipmentLines.md#parentdocument) | [Documents](General.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [ParentSalesOrderLine](Logistics.Shipment.ShipmentLines.md#parentsalesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) | Sales order line which is shipped. `Required` `Filter(multi eq)` |
| [QuantityUnit](Logistics.Shipment.ShipmentLines.md#quantityunit) | [MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [SerialNumber](Logistics.Shipment.ShipmentLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the shipped product. null means that serial number is unknown or not applicable. `Filter(multi eq)` |
| [Shipment](Logistics.Shipment.ShipmentLines.md#shipment) | [Shipments](Logistics.Shipment.Shipments.md) | The `Shipment`(Logistics.Shipment.ShipmentLines.md#shipment) to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ShipmentOrderLine](Logistics.Shipment.ShipmentLines.md#shipmentorderline) | [ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable) | Shipment order line for which this quantity is shipped. `Filter(multi eq)` |
| [StoreBin](Logistics.Shipment.ShipmentLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin from which to take the goods. `Filter(multi eq)` |
| [TransactionLine](Logistics.Shipment.ShipmentLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product. `Filter(multi eq)` |


## Attribute Details

### BoxCount

The count of boxes in which the goods are packaged. null means unknown.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Finished

True if this shipment should prohibit further shipments for the sales order line. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### GrossWeightkg

The gross weight of the whole line in kilogramms. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`IIF( obj.ParentSalesOrderLine.Product.ProductType.IsServiced, obj.ParentSalesOrderLine.Product.GuaranteePeriodDays, null)`
### Heightm

The height of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Lengthm

The length of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### LineNo

Line number, unique for the shipment. `Required`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineRequiredDeliveryDate

Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly.

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`obj.Shipment.RequiredDeliveryDate`

_Front-End Recalc Expressions:_  
`obj.Shipment.RequiredDeliveryDate`
### NetWeightkg

The net weight of the entire batch of goods in kilograms. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Notes

Specific notes for this line.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### PalletNo

The number of the pallet in which the goods are packaged. null means unknown.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(multi eq)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Quantity

The quantity to be shipped. `Unit: QuantityUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.Quantity`
### QuantityBase

The equivalence of Quantity in the base measurement category of the product. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### Volumel

The volume in litres of the whole batch. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Widthm

The width of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Document

The `Shipment`(Logistics.Shipment.ShipmentLines.md#shipment) to which this ShipmentLine belongs. `Required` `Filter(multi eq)`

_Type_: **[Shipments](Logistics.Shipment.Shipments.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### Lot

The store lot from which to take the goods. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.Lot`
### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### ParentSalesOrderLine

Sales order line which is shipped. `Required` `Filter(multi eq)`

_Type_: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.QuantityUnit`
### SerialNumber

The serial number of the shipped product. null means that serial number is unknown or not applicable. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Shipment

The `Shipment`(Logistics.Shipment.ShipmentLines.md#shipment) to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Shipments](Logistics.Shipment.Shipments.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### ShipmentOrderLine

Shipment order line for which this quantity is shipped. `Filter(multi eq)`

_Type_: **[ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### StoreBin

The store bin from which to take the goods. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### TransactionLine

The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product. `Filter(multi eq)`

_Type_: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.ShipmentLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.ShipmentLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Shipment_ShipmentLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_ShipmentLines?$top=10>

