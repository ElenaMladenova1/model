# Applications.AssetManagement.ManagedAssets

Contains the managed assets. The management of assets include maintenance planning and execution, location assignments tracking, etc. Entity: Eam_Managed_Assets (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssets.md#Id) | guid |  
| [Code](Applications.AssetManagement.ManagedAssets.md#Code) | string | Unique code of the managed asset. The code is unique among all managed assets in the same enterprise company. [Required] [Filter(eq;like)] 
| [Name](Applications.AssetManagement.ManagedAssets.md#Name) | [MultilanguageString](../data-types/MultilanguageString.md) | Name of the managed asset (multi-language). [Required] [Filter(eq;like)] 
| [Notes](Applications.AssetManagement.ManagedAssets.md#Notes) | string (nullable) | Notes for this ManagedAsset. 
| [RegistrationNumber](Applications.AssetManagement.ManagedAssets.md#RegistrationNumber) | string (nullable) | Registration number of the asset with the national registration authorities. null means the registation number is unknown or N/A. [Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.AssetManagement.ManagedAssets.md#EnterpriseCompany) | [General.EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company to which the managed asset belongs. [Required] [Filter(multi eq)] |
| [ManagedAssetGroup](Applications.AssetManagement.ManagedAssets.md#ManagedAssetGroup) | [Applications.AssetManagement.ManagedAssetGroups](Applications.AssetManagement.ManagedAssetGroups.md) | The organizational group of the asset. Used for organizational purposes only. [Required] [Filter(multi eq)] |
| [ManagedAssetType](Applications.AssetManagement.ManagedAssets.md#ManagedAssetType) | [Applications.AssetManagement.ManagedAssetTypes](Applications.AssetManagement.ManagedAssetTypes.md) | The type of the asset. Determines the tracked parameters for the asset, the applicable maintenance types, etc. [Required] [Filter(multi eq)] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Locations | [Applications.AssetManagement.ManagedAssetLocations](Applications.AssetManagement.ManagedAssetLocations.md) | List of [ManagedAssetLocation](Applications.AssetManagement.ManagedAssetLocations.md) child objects, based on the [Applications.AssetManagement.ManagedAssetLocation.ManagedAsset](Applications.AssetManagement.ManagedAssetLocations.md#ManagedAsset) back reference 
| MaintenanceSchedules | [Applications.AssetManagement.ManagedAssetMaintenanceSchedules](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md) | List of [ManagedAssetMaintenanceSchedule](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md) child objects, based on the [Applications.AssetManagement.ManagedAssetMaintenanceSchedule.ManagedAsset](Applications.AssetManagement.ManagedAssetMaintenanceSchedules.md#ManagedAsset) back reference 
| ParameterValues | [Applications.AssetManagement.ManagedAssetParameterValues](Applications.AssetManagement.ManagedAssetParameterValues.md) | List of [ManagedAssetParameterValue](Applications.AssetManagement.ManagedAssetParameterValues.md) child objects, based on the [Applications.AssetManagement.ManagedAssetParameterValue.ManagedAsset](Applications.AssetManagement.ManagedAssetParameterValues.md#ManagedAsset) back reference 
| ScheduledMaintenances | [Applications.AssetManagement.ManagedAssetScheduledMaintenances](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md) | List of [ManagedAssetScheduledMaintenance](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md) child objects, based on the [Applications.AssetManagement.ManagedAssetScheduledMaintenance.ManagedAsset](Applications.AssetManagement.ManagedAssetScheduledMaintenances.md#ManagedAsset) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Code

> Unique code of the managed asset. The code is unique among all managed assets in the same enterprise company. [Required] [Filter(eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Name

> Name of the managed asset (multi-language). [Required] [Filter(eq;like)]

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Notes

> Notes for this ManagedAsset.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### RegistrationNumber

> Registration number of the asset with the national registration authorities. null means the registation number is unknown or N/A. [Filter(eq;like)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


## Reference Details

### EnterpriseCompany

> The enterprise company to which the managed asset belongs. [Required] [Filter(multi eq)]

_Type_: **[General.EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ManagedAssetGroup

> The organizational group of the asset. Used for organizational purposes only. [Required] [Filter(multi eq)]

_Type_: **[Applications.AssetManagement.ManagedAssetGroups](Applications.AssetManagement.ManagedAssetGroups.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ManagedAssetType

> The type of the asset. Determines the tracked parameters for the asset, the applicable maintenance types, etc. [Required] [Filter(multi eq)]

_Type_: **[Applications.AssetManagement.ManagedAssetTypes](Applications.AssetManagement.ManagedAssetTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssets erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssets erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.AssetManagement.ManagedAssets erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssets?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssets?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Eam_Managed_Assets?$top=10>
