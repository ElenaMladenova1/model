# Applications.AssetManagement.MaintenanceOrderLines

Contains the types of maintenance and maintained assets in the maintenance orders. Entity: Eam_Maintenance_Order_Lines (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.MaintenanceOrderLines.md#Id) | guid |  
| [LineNo](Applications.AssetManagement.MaintenanceOrderLines.md#LineNo) | int32 | Consecutive line number, unique within the maintenance order. [Required] 
| [NextServiceDate](Applications.AssetManagement.MaintenanceOrderLines.md#NextServiceDate) | date (nullable) | Specifies, that the maintenance required a specific date for the next maintenance. null means that default scheduling should be used. 
| [NextServiceTrackedParameterValue](Applications.AssetManagement.MaintenanceOrderLines.md#NextServiceTrackedParameterValue) | int32 (nullable) | Specifies, that the maintenance required the next maintenance to be performed on a specific value of the tracked parameter. null means that default scheduling should be used. 
| [Notes](Applications.AssetManagement.MaintenanceOrderLines.md#Notes) | string (nullable) | Notes for this MaintenanceOrderLine. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenanceOrder](Applications.AssetManagement.MaintenanceOrderLines.md#MaintenanceOrder) | [Applications.AssetManagement.MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md) | The [MaintenanceOrder](Applications.AssetManagement.MaintenanceOrderLines.md#MaintenanceOrder) to which this MaintenanceOrderLine belongs. [Required] [Filter(multi eq)] [Owner] |
| [MaintenanceType](Applications.AssetManagement.MaintenanceOrderLines.md#MaintenanceType) | [Applications.AssetManagement.MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | The type of maintenance performed. [Required] [Filter(multi eq)] |
| [ManagedAsset](Applications.AssetManagement.MaintenanceOrderLines.md#ManagedAsset) | [Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The maintained asset. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### LineNo

> Consecutive line number, unique within the maintenance order. [Required]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`(obj.MaintenanceOrder.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.MaintenanceOrder.Lines.Select(c => c.LineNo).DefaultIfEmpty(0).Max() + 10)`
### NextServiceDate

> Specifies, that the maintenance required a specific date for the next maintenance. null means that default scheduling should be used.

_Type_: **date (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### NextServiceTrackedParameterValue

> Specifies, that the maintenance required the next maintenance to be performed on a specific value of the tracked parameter. null means that default scheduling should be used.

_Type_: **int32 (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Notes

> Notes for this MaintenanceOrderLine.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### MaintenanceOrder

> The [MaintenanceOrder](Applications.AssetManagement.MaintenanceOrderLines.md#MaintenanceOrder) to which this MaintenanceOrderLine belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Applications.AssetManagement.MaintenanceOrders](Applications.AssetManagement.MaintenanceOrders.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### MaintenanceType

> The type of maintenance performed. [Required] [Filter(multi eq)]

_Type_: **[Applications.AssetManagement.MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ManagedAsset

> The maintained asset. [Required] [Filter(multi eq)]

_Type_: **[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.AssetManagement.MaintenanceOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.AssetManagement.MaintenanceOrderLines erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.AssetManagement.MaintenanceOrderLines erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_AssetManagement_MaintenanceOrderLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_MaintenanceOrderLines?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Eam_Maintenance_Order_Lines?$top=10>
