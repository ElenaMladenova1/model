# Applications.AssetManagement.ManagedAssetLocations

Contains the locations to which the assets are assigned at various moments in time. Entity: Eam_Managed_Asset_Locations (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssetLocations.md#Id) | guid |  
| [FromDate](Applications.AssetManagement.ManagedAssetLocations.md#FromDate) | date | The date on which the asset is assigned to the location. [Required] [Default(Now)] 
| [Notes](Applications.AssetManagement.ManagedAssetLocations.md#Notes) | string (nullable) | Might contain additional notes for the exact location of the asset within the enterprise company location. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompanyLocation](Applications.AssetManagement.ManagedAssetLocations.md#EnterpriseCompanyLocation) | [General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md) | The enterprise company location, where the asset is assigned. [Required] [Filter(multi eq)] |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetLocations.md#ManagedAsset) | [Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The asset, whose location is recorded. [Required] [Filter(multi eq)] [Owner] |
| [ResponsiblePerson](Applications.AssetManagement.ManagedAssetLocations.md#ResponsiblePerson) | [General.Contacts.Persons](General.Contacts.Persons.md) (nullable) | The responsible person, to which the asset is assigned. null when the asset is not assigned to any particular responsible person. [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### FromDate

> The date on which the asset is assigned to the location. [Required] [Default(Now)]

_Type_: **date**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  

### Notes

> Might contain additional notes for the exact location of the asset within the enterprise company location.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### EnterpriseCompanyLocation

> The enterprise company location, where the asset is assigned. [Required] [Filter(multi eq)]

_Type_: **[General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ManagedAsset

> The asset, whose location is recorded. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ResponsiblePerson

> The responsible person, to which the asset is assigned. null when the asset is not assigned to any particular responsible person. [Filter(multi eq)]

_Type_: **[General.Contacts.Persons](General.Contacts.Persons.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssetLocations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.AssetManagement.ManagedAssetLocations erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.AssetManagement.ManagedAssetLocations erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetLocations?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetLocations?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Eam_Managed_Asset_Locations?$top=10>
