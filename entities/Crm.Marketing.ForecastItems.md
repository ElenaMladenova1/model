---
uid: Crm.Marketing.ForecastItems
---
# Crm.Marketing.ForecastItems Entity

**Namespace:** [Crm.Marketing](Crm.Marketing.md)  

Forecast items form demand in MRP calculations. Entity: Crm_Forecast_Items

## Default Visualization
Default Display Text Format:  
_{Id}: {QuantityValue}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Marketing.ForecastItems](Crm.Marketing.ForecastItems.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Date](Crm.Marketing.ForecastItems.md#date) | datetime | The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period. `Required` `Filter(ge;le)` 
| [DisplayText](Crm.Marketing.ForecastItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Marketing.ForecastItems.md#id) | guid |  
| [ObjectVersion](Crm.Marketing.ForecastItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Crm.Marketing.ForecastItems.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The forecasted sales quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Country](Crm.Marketing.ForecastItems.md#country) | [Countries](General.Geography.Countries.md) (nullable) | The country for which the forecast is made. When null, the forecast is country neutral. `Filter(multi eq)` |
| [Customer](Crm.Marketing.ForecastItems.md#customer) | [Customers](Crm.Customers.md) (nullable) | The customer for which the forecast is made. When null, the forecast is not for any specfic customer. `Filter(multi eq)` |
| [Dealer](Crm.Marketing.ForecastItems.md#dealer) | [Dealers](Crm.Dealers.md) (nullable) | The dealer for which the forecast is made. When null, the forecast is not for any specfic dealer. `Filter(multi eq)` |
| [Product](Crm.Marketing.ForecastItems.md#product) | [Products](General.Products.Products.md) | The product for which the forecast is made. `Required` `Filter(multi eq)` |
| [SalesPerson](Crm.Marketing.ForecastItems.md#salesperson) | [SalesPersons](Crm.SalesPersons.md) (nullable) | The sales person for which the forecast is made. When null, the forecast is not for any specfic sales person. `Filter(multi eq)` |
| [Store](Crm.Marketing.ForecastItems.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store which is expected to sell the products. `Required` `Filter(multi eq)` |


## Attribute Details

### Date

The date for which the sales is forecasted. When forecasting for a period, this contains the first date of the period. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Quantity

The forecasted sales quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  


## Reference Details

### Country

The country for which the forecast is made. When null, the forecast is country neutral. `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Customer

The customer for which the forecast is made. When null, the forecast is not for any specfic customer. `Filter(multi eq)`

_Type_: **[Customers](Crm.Customers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Dealer

The dealer for which the forecast is made. When null, the forecast is not for any specfic dealer. `Filter(multi eq)`

_Type_: **[Dealers](Crm.Dealers.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The product for which the forecast is made. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### SalesPerson

The sales person for which the forecast is made. When null, the forecast is not for any specfic sales person. `Filter(multi eq)`

_Type_: **[SalesPersons](Crm.SalesPersons.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Store

The store which is expected to sell the products. `Required` `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
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

[!list limit=1000 erp.entity=Crm.Marketing.ForecastItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.ForecastItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Marketing_ForecastItems?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Marketing_ForecastItems?$top=10>

