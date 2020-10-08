# Applications.AssetManagement.ManagedAssetScheduledMaintenances

Contains the scheduled maintenances for the managed assets. Each maintenance can be planned based on date, parameter value or both. Past maintenance plans are kept only for reference and can be deleted at any time. Entity: Eam_Managed_Asset_Scheduled_Maintenances (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#Id) | guid |  
| [Date](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#Date) | date (nullable) | The date, when the maintenance is planned. null means, that the plan is not related to date, but to tracked parameter value. If both date and parameter are specified, the maintenance is performed when any of the conditions is met. [Filter(multi eq;ge;le)] 
| [IsDismissed](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#IsDismissed) | boolean | Specifies whether the notification for the maintenance is dismissed and the planner has decided the course of action. [Required] [Default(false)] [Filter(multi eq)] 
| [Notes](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#Notes) | string (nullable) | Notes for this ManagedAssetScheduledMaintenance. 
| [TrackedParameterValue](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#TrackedParameterValue) | int32 (nullable) | The value of the tracked parameter (as specified in the maintenance type) at which the maintenance will be performed. For example, for a car, we can schedule maintenance at 20,000 km mileage. null means, that the maintenance is not planned based on parameter, but rather only for date. If both date and parameter are specified, the maintenance is performed when any of the conditions is met. [Filter(multi eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaintenanceType](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#MaintenanceType) | [Applications.AssetManagement.MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md) | The type of maintenance, which will be performed. [Required] [Filter(multi eq)] |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#ManagedAsset) | [Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The asset, which will be maintained. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Date

> The date, when the maintenance is planned. null means, that the plan is not related to date, but to tracked parameter value. If both date and parameter are specified, the maintenance is performed when any of the conditions is met. [Filter(multi eq;ge;le)]

_Type_: **date (nullable)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  

### IsDismissed

> Specifies whether the notification for the maintenance is dismissed and the planner has decided the course of action. [Required] [Default(false)] [Filter(multi eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Notes

> Notes for this ManagedAssetScheduledMaintenance.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TrackedParameterValue

> The value of the tracked parameter (as specified in the maintenance type) at which the maintenance will be performed. For example, for a car, we can schedule maintenance at 20,000 km mileage. null means, that the maintenance is not planned based on parameter, but rather only for date. If both date and parameter are specified, the maintenance is performed when any of the conditions is met. [Filter(multi eq;ge;le)]

_Type_: **int32 (nullable)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  


## Reference Details

### MaintenanceType

> The type of maintenance, which will be performed. [Required] [Filter(multi eq)]

_Type_: **[Applications.AssetManagement.MaintenanceTypes](Applications.AssetManagement.MaintenanceTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ManagedAsset

> The asset, which will be maintained. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssetScheduledMaintenances erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssetScheduledMaintenances erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.AssetManagement.ManagedAssetScheduledMaintenances erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetScheduledMaintenances?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetScheduledMaintenances?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Eam_Managed_Asset_Scheduled_Maintenances?$top=10>
