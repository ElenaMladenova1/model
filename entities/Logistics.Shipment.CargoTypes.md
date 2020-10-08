# Logistics.Shipment.CargoTypes

Represents a cargo type. Different cargo types might require different types of vehicles or modes of transportartion. Entity: Log_Cargo_Types

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Shipment.CargoTypes.md#Id) | guid |  
| [Code](Logistics.Shipment.CargoTypes.md#Code) | string | The unique code of the CargoType. [Required] [Filter(eq;like)] [ORD] 
| [Name](Logistics.Shipment.CargoTypes.md#Name) | string | The name of this CargoType. [Required] [Filter(eq;like)] 
| [Notes](Logistics.Shipment.CargoTypes.md#Notes) | string (nullable) | Notes for this CargoType. 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Code

> The unique code of the CargoType. [Required] [Filter(eq;like)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  

### Name

> The name of this CargoType. [Required] [Filter(eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Notes

> Notes for this CargoType.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Logistics.Shipment.CargoTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Shipment.CargoTypes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Logistics.Shipment.CargoTypes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Shipment_CargoTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_CargoTypes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Log_Cargo_Types?$top=10>
