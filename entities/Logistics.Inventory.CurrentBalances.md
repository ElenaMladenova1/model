---
uid: Logistics.Inventory.CurrentBalances
---
# Logistics.Inventory.CurrentBalances View

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

The current inventory balances, grouped by storage key (Store, Product, Lot, etc.). Entity: Inv_Current_Balances

## Default Visualization
Default Display Text Format:  
_{BaseCostValue}: {EnterpriseCompanyId}_  
Default Search Member:  
_BaseCostValue_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.CurrentBalances](Logistics.Inventory.CurrentBalances.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCost](Logistics.Inventory.CurrentBalances.md#basecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(ge;le)` 
| [ProductCost](Logistics.Inventory.CurrentBalances.md#productcost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required` 
| [QuantityBase](Logistics.Inventory.CurrentBalances.md#quantitybase) | [Quantity (38, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)` `ReadOnly` 
| [StoreCost](Logistics.Inventory.CurrentBalances.md#storecost) | [Amount (38, 2)](../data-types.md#amount) | The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.CurrentBalances.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id` |
| [Lot](Logistics.Inventory.CurrentBalances.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Lot_Id` |
| [Product](Logistics.Inventory.CurrentBalances.md#product) | [Products](General.Products.Products.md) | The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Id` |
| [ProductVariant](Logistics.Inventory.CurrentBalances.md#productvariant) | [ProductVariants](General.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Product_Variant_Id` |
| [SerialNumber](Logistics.Inventory.CurrentBalances.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Serial_Number_Id` |
| [Store](Logistics.Inventory.CurrentBalances.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id` |
| [StoreBin](Logistics.Inventory.CurrentBalances.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_<br />Lines_Table.Store_Bin_Id` |


## Attribute Details

### BaseCost

The cost of the inventory in base currency of the enterprise company. `Currency: EnterpriseCompany.BaseCurrency` `Required` `Filter(ge;le)`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### ProductCost

The cost of the inventory in the products currency. `Currency: Product.CostingCurrency` `Required`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)` `ReadOnly`

_Type_: **[Quantity (38, 3)](../data-types.md#quantity)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### StoreCost

The cost of the inventory in the stores currency. `Currency: Store.Currency` `Required`

_Type_: **[Amount (38, 2)](../data-types.md#amount)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### EnterpriseCompany

The enterprise company which issued the document. `Required` `Filter(multi eq)` `Inherited from Gen_Documents_Table.Enterprise_Company_Id`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Inherited From_: **Gen_Documents_Table.Enterprise_Company_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Lot_Id`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Inherited From_: **Inv_Transaction_Lines_Table.Lot_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The item that was received/issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Id`

_Type_: **[Products](General.Products.Products.md)**  
_Inherited From_: **Inv_Transaction_Lines_Table.Product_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Product_Variant_Id`

_Type_: **[ProductVariants](General.ProductVariants.md) (nullable)**  
_Inherited From_: **Inv_Transaction_Lines_Table.Product_Variant_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### SerialNumber

Item serial number for serialized items. null for non-serialized items. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Serial_Number_Id`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Inherited From_: **Inv_Transaction_Lines_Table.Serial_Number_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### Store

The store from which the goods are received or issued. `Required` `Filter(multi eq)` `Inherited from Inv_Transactions_Table.Store_Id`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Inherited From_: **Inv_Transactions_Table.Store_Id**  
_Supported Filters_: **Equals, EqualsIn**  

### StoreBin

Store bin, from/to which the transaction was performed. `Filter(multi eq)` `Inherited from Inv_Transaction_Lines_Table.Store_Bin_Id`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Inherited From_: **Inv_Transaction_Lines_Table.Store_Bin_Id**  
_Supported Filters_: **Equals, EqualsIn**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_CurrentBalances?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_CurrentBalances?$top=10>

