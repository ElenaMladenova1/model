# Systems.Security.UserGroups

Contains the user group members. Entity: Sec_User_Groups

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.UserGroups.md#Id) | guid |  

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Group](Systems.Security.UserGroups.md#Group) | [Systems.Security.Groups](Systems.Security.Groups.md) | The group, in which the user is included. [Required] [Filter(multi eq)] |
| [User](Systems.Security.UserGroups.md#User) | [Systems.Security.Users](Systems.Security.Users.md) | The [User](Systems.Security.UserGroups.md#User) to which this UserGroup belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  


## Reference Details

### Group

> The group, in which the user is included. [Required] [Filter(multi eq)]

_Type_: **[Systems.Security.Groups](Systems.Security.Groups.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### User

> The [User](Systems.Security.UserGroups.md#User) to which this UserGroup belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Systems.Security.Users](Systems.Security.Users.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Systems.Security.UserGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Security.UserGroups erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Security.UserGroups erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Security_UserGroups?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Security_UserGroups?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Sec_User_Groups?$top=10>
