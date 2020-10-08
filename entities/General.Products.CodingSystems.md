# General.Products.CodingSystems

Coding systems categorize additional product codes. Entity: Gen_Coding_Systems

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.CodingSystems.md#Id) | guid |  
| [Name](General.Products.CodingSystems.md#Name) | [MultilanguageString](../data-types/MultilanguageString.md) | The name of this CodingSystem. [Required] [Filter(eq;like)] 
| [Description](General.Products.CodingSystems.md#Description) | string (nullable) | The description of this CodingSystem. 
| [IsUnique](General.Products.CodingSystems.md#IsUnique) | boolean | True when the coding system can contain only unique product codes. false - duplicate product codes are allowed. [Required] [Default(true)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultMeasurementUnit](General.Products.CodingSystems.md#DefaultMeasurementUnit) | [General.MeasurementUnits](General.MeasurementUnits.md) (nullable) | When not null, specifies a measurement unit to be used as default, instead of the products default unit. [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Name

> The name of this CodingSystem. [Required] [Filter(eq;like)]

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Description

> The description of this CodingSystem.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsUnique

> True when the coding system can contain only unique product codes. false - duplicate product codes are allowed. [Required] [Default(true)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  


## Reference Details

### DefaultMeasurementUnit

> When not null, specifies a measurement unit to be used as default, instead of the products default unit. [Filter(multi eq)]

_Type_: **[General.MeasurementUnits](General.MeasurementUnits.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=General.Products.CodingSystems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=General.Products.CodingSystems erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=General.Products.CodingSystems erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Products_CodingSystems?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Products_CodingSystems?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Gen_Coding_Systems?$top=10>
