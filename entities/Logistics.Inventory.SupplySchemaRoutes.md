# Logistics.Inventory.SupplySchemaRoutes

Obsolete. Not used. Entity: Inv_Supply_Schema_Routes

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.SupplySchemaRoutes.md#Id) | guid |  
| [Notes](Logistics.Inventory.SupplySchemaRoutes.md#Notes) | string (nullable) | Notes for this SupplySchemaRoute. 
| [SchemaXML](Logistics.Inventory.SupplySchemaRoutes.md#SchemaXML) | string (nullable) | Obsolete. Not used. (Used by the schematic control). 
| [TransitTimeDays](Logistics.Inventory.SupplySchemaRoutes.md#TransitTimeDays) | int32 | Obsolete. Not used. (Time needed for the delivery of the goods using this route). [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DestinationStore](Logistics.Inventory.SupplySchemaRoutes.md#DestinationStore) | [Logistics.Inventory.Stores](Logistics.Inventory.Stores.md) | Obsolete. Not used. [Required] [Filter(multi eq)] |
| [SourceStore](Logistics.Inventory.SupplySchemaRoutes.md#SourceStore) | [Logistics.Inventory.Stores](Logistics.Inventory.Stores.md) | Obsolete. Not used. [Required] [Filter(multi eq)] |
| [SupplySchema](Logistics.Inventory.SupplySchemaRoutes.md#SupplySchema) | [Logistics.Inventory.SupplySchemata](Logistics.Inventory.SupplySchemata.md) | The [SupplySchema](Logistics.Inventory.SupplySchemaRoutes.md#SupplySchema) to which this SupplySchemaRoute belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Notes

> Notes for this SupplySchemaRoute.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### SchemaXML

> Obsolete. Not used. (Used by the schematic control).

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TransitTimeDays

> Obsolete. Not used. (Time needed for the delivery of the goods using this route). [Required] [Default(0)]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### DestinationStore

> Obsolete. Not used. [Required] [Filter(multi eq)]

_Type_: **[Logistics.Inventory.Stores](Logistics.Inventory.Stores.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### SourceStore

> Obsolete. Not used. [Required] [Filter(multi eq)]

_Type_: **[Logistics.Inventory.Stores](Logistics.Inventory.Stores.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### SupplySchema

> The [SupplySchema](Logistics.Inventory.SupplySchemaRoutes.md#SupplySchema) to which this SupplySchemaRoute belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Logistics.Inventory.SupplySchemata](Logistics.Inventory.SupplySchemata.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Logistics.Inventory.SupplySchemaRoutes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Inventory.SupplySchemaRoutes erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Logistics.Inventory.SupplySchemaRoutes erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_SupplySchemaRoutes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_SupplySchemaRoutes?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Inv_Supply_Schema_Routes?$top=10>
