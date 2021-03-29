---
uid: Logistics.Procurement.PurchaseProductPrices
---
# Logistics.Procurement.PurchaseProductPrices Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains purchase prices of the products. Used for automatically loading unit prices in the purchase documents. Entity: Scm_Purchase_Product_Prices

## Default Visualization
Default Display Text Format:  
_{Id}_  
Default Search Member:  
_Id_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](Logistics.Procurement.PurchaseProductPrices.md#fromdate) | datetime __nullable__ | Starting date of validity of the price. `Filter(eq;ge;le)` 
| [Id](Logistics.Procurement.PurchaseProductPrices.md#id) | guid |  
| [MaxQuantity](Logistics.Procurement.PurchaseProductPrices.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum quantity for which this price is valid in the Price_Quantity_<br />Measurement_Unit. `Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [MinQuantity](Logistics.Procurement.PurchaseProductPrices.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit). `Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [Notes](Logistics.Procurement.PurchaseProductPrices.md#notes) | string (254) __nullable__ | Notes for this PurchaseProductPrice. 
| [Price](Logistics.Procurement.PurchaseProductPrices.md#price) | [Amount (13, 5)](../data-types.md#amount) | Price in the specified currency and for the specified quantity. `Currency: Currency` `Required` `Default(0)` 
| [PriceQuantity](Logistics.Procurement.PurchaseProductPrices.md#pricequantity) | [Quantity (10, 3)](../data-types.md#quantity) | The quantity of the product for which the price is specified. `Unit: PriceQuantityMeasurement<br />Unit` `Required` `Default(1)` 
| [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | Priority of the price comparative to other prices. `Required` `Default(2)` `Filter(multi eq)` 
| [ThruDate](Logistics.Procurement.PurchaseProductPrices.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of the validity of the price. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Logistics.Procurement.PurchaseProductPrices.md#currency) | [Currencies](General.Currencies.md) | The currency of the price. `Required` `Filter(multi eq)` |
| [EnterpriseCompany](Logistics.Procurement.PurchaseProductPrices.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies. `Filter(multi eq)` |
| [PriceQuantityMeasurement<br />Unit](Logistics.Procurement.PurchaseProductPrices.md#pricequantitymeasurementunit) | [MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of Price_Quantity. `Required` `Filter(multi eq)` |
| [Product](Logistics.Procurement.PurchaseProductPrices.md#product) | [Products](General.Products.Products.md) | The product for which a purchase price will be defined. `Required` `Filter(multi eq)` |
| [PurchasePriceList](Logistics.Procurement.PurchaseProductPrices.md#purchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable) | When not null, specifies that this price is valid only when the purchase document is set to work with the specified price list. `Filter(multi eq)` |
| [Supplier](Logistics.Procurement.PurchaseProductPrices.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | When not null, specifies that the price is valid only for the specified supplier. `Filter(multi eq)` |


## Attribute Details

### FromDate

Starting date of validity of the price. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### MaxQuantity

Maximum quantity for which this price is valid in the Price_Quantity_Measurement_Unit. `Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### MinQuantity

Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit). `Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### Notes

Notes for this PurchaseProductPrice.

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### Price

Price in the specified currency and for the specified quantity. `Currency: Currency` `Required` `Default(0)`

_Type_: **[Amount (13, 5)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### PriceQuantity

The quantity of the product for which the price is specified. `Unit: PriceQuantityMeasurementUnit` `Required` `Default(1)`

_Type_: **[Quantity (10, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### Priority

Priority of the price comparative to other prices. `Required` `Default(2)` `Filter(multi eq)`

_Type_: **[Priority](Logistics.Procurement.PurchaseProductPrices.md#priority)**  
Allowed values for the `Priority`(Logistics.Procurement.PurchaseProductPrices.md#priority) data attribute  
_Allowed Values (Logistics.Procurement.PurchaseProductPricesRepository.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Two | Two value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Three' |
| Four | Four value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Four' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **2**  

### ThruDate

Ending date (inclusive) of the validity of the price. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  


## Reference Details

### Currency

The currency of the price. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### EnterpriseCompany

Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### PriceQuantityMeasurementUnit

The measurement unit of Price_Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`obj.Product.BaseUnit.IfNullThen( obj.PriceQuantityMeasurementUnit)`
### Product

The product for which a purchase price will be defined. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### PurchasePriceList

When not null, specifies that this price is valid only when the purchase document is set to work with the specified price list. `Filter(multi eq)`

_Type_: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Supplier

When not null, specifies that the price is valid only for the specified supplier. `Filter(multi eq)`

_Type_: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Logistics.Procurement.PurchaseProductPrices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Procurement.PurchaseProductPrices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseProductPrices?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseProductPrices?$top=10>

