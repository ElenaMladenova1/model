# Systems.Core.ObjectChangesets

A set of changes, performed in one request. Entity: Sys_Object_Changesets (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ObjectChangesets.md#Id) | guid |  
| [ApplicationName](Systems.Core.ObjectChangesets.md#ApplicationName) | string (nullable) | The application which requested the change. null when it is unknown. [Filter(eq)] 
| [ServerVersion](Systems.Core.ObjectChangesets.md#ServerVersion) | string | The version of the application server at the time of the change. [Required] 
| [TimeUtc](Systems.Core.ObjectChangesets.md#TimeUtc) | datetime | Date and time (in Utc) when the changeset was processed by the server. [Required] [Default(NowUtc)] [Filter(eq;ge;le)] [ORD] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [User](Systems.Core.ObjectChangesets.md#User) | [Systems.Security.Users](Systems.Security.Users.md) (nullable) | The user which initiated the change. null when it is unknown. [Filter(multi eq)] |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ObjectChanges | [Systems.Core.ObjectChanges](Systems.Core.ObjectChanges.md) | List of [ObjectChange](Systems.Core.ObjectChanges.md) child objects, based on the [Systems.Core.ObjectChange.ObjectChangeset](Systems.Core.ObjectChanges.md#ObjectChangeset) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### ApplicationName

> The application which requested the change. null when it is unknown. [Filter(eq)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### ServerVersion

> The version of the application server at the time of the change. [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TimeUtc

> Date and time (in Utc) when the changeset was processed by the server. [Required] [Default(NowUtc)] [Filter(eq;ge;le)] [ORD]

_Type_: **datetime**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  


## Reference Details

### User

> The user which initiated the change. null when it is unknown. [Filter(multi eq)]

_Type_: **[Systems.Security.Users](Systems.Security.Users.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Systems.Core.ObjectChangesets erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Core.ObjectChangesets erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Core.ObjectChangesets erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_ObjectChangesets?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_ObjectChangesets?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Sys_Object_Changesets?$top=10>
