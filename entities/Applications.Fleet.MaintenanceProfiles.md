# Applications.Fleet.MaintenanceProfiles

Profiles contain multiple maintenance plans and can be assigned directly to a vehicle. Entity: Fleet_Maintenance_Profiles

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Fleet.MaintenanceProfiles.md#Id) | guid |  
| [IsActive](Applications.Fleet.MaintenanceProfiles.md#IsActive) | boolean | True if the profile is active and can be assigned to vehicles. However, if a profile is already assigned to a vehicle, it will still work even if it is de-activated. [Required] [Default(true)] (Introduced in version 18.2.100.0) 
| [Code](Applications.Fleet.MaintenanceProfiles.md#Code) | string | The unique code of the MaintenanceProfile. [Required] 
| [Name](Applications.Fleet.MaintenanceProfiles.md#Name) | string | Name of the maintenance profile (Multilanguage). [Required] 
| [Notes](Applications.Fleet.MaintenanceProfiles.md#Notes) | string (nullable) | Notes for this MaintenanceProfile. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Plans | [Applications.Fleet.MaintenanceProfilePlans](Applications.Fleet.MaintenanceProfilePlans.md) | List of [MaintenanceProfilePlan](Applications.Fleet.MaintenanceProfilePlans.md) child objects, based on the [Applications.Fleet.MaintenanceProfilePlan.MaintenanceProfile](Applications.Fleet.MaintenanceProfilePlans.md#MaintenanceProfile) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### IsActive

> True if the profile is active and can be assigned to vehicles. However, if a profile is already assigned to a vehicle, it will still work even if it is de-activated. [Required] [Default(true)] (Introduced in version 18.2.100.0)

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### Code

> The unique code of the MaintenanceProfile. [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Name

> Name of the maintenance profile (Multilanguage). [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Notes

> Notes for this MaintenanceProfile.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.Fleet.MaintenanceProfiles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.Fleet.MaintenanceProfiles erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.Fleet.MaintenanceProfiles erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Fleet_MaintenanceProfiles?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Fleet_MaintenanceProfiles?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Fleet_Maintenance_Profiles?$top=10>
