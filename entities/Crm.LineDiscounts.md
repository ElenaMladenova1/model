---
uid: Crm.LineDiscounts
---
# Crm.LineDiscounts Entity

**Namespace:** [Crm](Crm.md)  

Discount policies for sales documents. Entity: Crm_Line_Discounts

## Default Visualization
Default Display Text Format:  
_{Id}_  
Default Search Member:  
_Id_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.LineDiscounts](Crm.LineDiscounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Crm.LineDiscounts.md#description) | string (50) __nullable__ | The description of the discount that is shown to the operator when he/she should choose between different discounts. `Filter(like)` 
| [DiscountPercent](Crm.LineDiscounts.md#discountpercent) | decimal (7, 6) | The discount percent that should be applied if all the matching criteria are met. `Required` `Default(0)` `Filter(ge;le)` 
| [FromDate](Crm.LineDiscounts.md#fromdate) | datetime __nullable__ | Starting date of validity of the discount. null means no from date restriction. `Filter(eq;ge;le)` 
| [Id](Crm.LineDiscounts.md#id) | guid |  
| [MaxQuantity](Crm.LineDiscounts.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or less than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [MinQuantity](Crm.LineDiscounts.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Apply the discount only if the quantity sold is equal to or more than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` 
| [Priority](Crm.LineDiscounts.md#priority) | [Priority](Crm.LineDiscounts.md#priority) | The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied. `Required` `Default(3)` 
| [ThruDate](Crm.LineDiscounts.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of validity of the discount. If null, the discount is valid forever. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Customer](Crm.LineDiscounts.md#customer) | [Customers](Crm.Customers.md) (nullable) | Apply the discount only if this is the customer. `Filter(multi eq)` |
| [CustomerType](Crm.LineDiscounts.md#customertype) | [CustomerTypes](Crm.CustomerTypes.md) (nullable) | Apply the discount only if the customer is of this customer type. `Filter(multi eq)` |
| [DistributionChannel](Crm.LineDiscounts.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | Apply the discount only when the sales document is on the specified channel. `Filter(multi eq)` |
| [EnterpriseCompany](Crm.LineDiscounts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, the policy is applied only for documents of the specified enterprise company . `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Crm.LineDiscounts.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When set, the policy is applied only for documents of the specified enterprise company location. `Filter(multi eq)` |
| [PriceList](Crm.LineDiscounts.md#pricelist) | [PriceLists](Crm.PriceLists.md) (nullable) | Apply the discount only if this price list is used. `Filter(multi eq)` |
| [Product](Crm.LineDiscounts.md#product) | [Products](General.Products.Products.md) (nullable) | Apply the discount only when this specific product is sold. `Filter(multi eq)` |
| [ProductGroup](Crm.LineDiscounts.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Apply the discount only if the product sold is contained in this product group or any of its sub-groups. `Filter(multi eq)` |
| [TargetGroup](Crm.LineDiscounts.md#targetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | Apply the discount only if the customer is included in this target group. `Filter(multi eq)` |


## Attribute Details

### Description

The description of the discount that is shown to the operator when he/she should choose between different discounts. `Filter(like)`

_Type_: **string (50) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  

### DiscountPercent

The discount percent that should be applied if all the matching criteria are met. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **decimal (7, 6)**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### FromDate

Starting date of validity of the discount. null means no from date restriction. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### MaxQuantity

Apply the discount only if the quantity sold is equal to or less than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### MinQuantity

Apply the discount only if the quantity sold is equal to or more than the specified here. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Priority

The priority of this discount policy. When selecting a discount for a sales document line, only the highest priority policy, matching the criteria is applied. `Required` `Default(3)`

_Type_: **[Priority](Crm.LineDiscounts.md#priority)**  
Generic enum type for Priority properties  
_Allowed Values (General.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Low | Low value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
| Medium | Medium value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Medium' |
| High | High value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **3**  

### ThruDate

Ending date (inclusive) of validity of the discount. If null, the discount is valid forever. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  


## Reference Details

### Customer

Apply the discount only if this is the customer. `Filter(multi eq)`

_Type_: **[Customers](Crm.Customers.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### CustomerType

Apply the discount only if the customer is of this customer type. `Filter(multi eq)`

_Type_: **[CustomerTypes](Crm.CustomerTypes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### DistributionChannel

Apply the discount only when the sales document is on the specified channel. `Filter(multi eq)`

_Type_: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### EnterpriseCompany

When not null, the policy is applied only for documents of the specified enterprise company . `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### EnterpriseCompanyLocation

When set, the policy is applied only for documents of the specified enterprise company location. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.EnterpriseCompanyLocation != null) AndAlso ( obj.EnterpriseCompanyLocation.Company != obj.EnterpriseCompany)), null, obj.EnterpriseCompanyLocation.Company)`
### PriceList

Apply the discount only if this price list is used. `Filter(multi eq)`

_Type_: **[PriceLists](Crm.PriceLists.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

Apply the discount only when this specific product is sold. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### ProductGroup

Apply the discount only if the product sold is contained in this product group or any of its sub-groups. `Filter(multi eq)`

_Type_: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### TargetGroup

Apply the discount only if the customer is included in this target group. `Filter(multi eq)`

_Type_: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list limit=1000 erp.entity=Crm.LineDiscounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.LineDiscounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_LineDiscounts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_LineDiscounts?$top=10>

