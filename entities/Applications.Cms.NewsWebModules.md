# Applications.Cms.NewsWebModules

Represents a web module, containing news. Entity: Cms_News_Web_Modules

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Cms.NewsWebModules.md#Id) | guid |  
| [IsPublished](Applications.Cms.NewsWebModules.md#IsPublished) | boolean | Specifies whether the module is published and will be showed in the web site. [Required] [Default(false)] [Filter(eq)] 
| [LocalUrl](Applications.Cms.NewsWebModules.md#LocalUrl) | string (nullable) | The local Module Url. The full Url of a module is formed based on the sites Base Url, the local Urls of all parent modules and the module Local Url. Null means that the web Module is the default web module within the parent path. [Filter(like)] 
| [ModulePicture](Applications.Cms.NewsWebModules.md#ModulePicture) | byte[] (nullable) | Default picture. Used for picture links, small module icons, etc. PNG format is suggested. 
| [ModuleType](Applications.Cms.NewsWebModules.md#ModuleType) | [Applications.Cms.WebModulesRepository.ModuleType](Applications.Cms.NewsWebModules.md#ModuleType) | Specifies the content handler. The content handler is responsible for generating the actual web page content. Module Types include Category, Static, News, Product, etc. [Required] [Filter(like)] 
| [Name](Applications.Cms.NewsWebModules.md#Name) | string | Multilanguage Module name. This is used as a title when displaying the web Module. [Required] [Filter(like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Parent](Applications.Cms.NewsWebModules.md#Parent) | [Applications.Cms.WebModules](Applications.Cms.WebModules.md) (nullable) | The parent web Module. It can only be a module with Module Type = Category. Null means that the web Module is root web Module. [Filter(multi eq)] |
| [WebSite](Applications.Cms.NewsWebModules.md#WebSite) | [Applications.Cms.WebSites](Applications.Cms.WebSites.md) | The web site to which the module belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### IsPublished

> Specifies whether the module is published and will be showed in the web site. [Required] [Default(false)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### LocalUrl

> The local Module Url. The full Url of a module is formed based on the sites Base Url, the local Urls of all parent modules and the module Local Url. Null means that the web Module is the default web module within the parent path. [Filter(like)]

_Type_: **string (nullable)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### ModulePicture

> Default picture. Used for picture links, small module icons, etc. PNG format is suggested.

_Type_: **byte[] (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ModuleType

> Specifies the content handler. The content handler is responsible for generating the actual web page content. Module Types include Category, Static, News, Product, etc. [Required] [Filter(like)]

_Type_: **[Applications.Cms.WebModulesRepository.ModuleType](Applications.Cms.NewsWebModules.md#ModuleType)**  
Allowed values for the [ModuleType](Applications.Cms.WebModules.md#ModuleType) data attribute  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| CategoryPage | CategoryPage value. Stored as 'CAT'. <br /> _Database Value:_ 'CAT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'CategoryPage' |
| Static | Static value. Stored as 'STA'. <br /> _Database Value:_ 'STA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Static' |
| News | News value. Stored as 'NEW'. <br /> _Database Value:_ 'NEW' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'News' |

_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### Name

> Multilanguage Module name. This is used as a title when displaying the web Module. [Required] [Filter(like)]

_Type_: **string**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  


## Reference Details

### Parent

> The parent web Module. It can only be a module with Module Type = Category. Null means that the web Module is root web Module. [Filter(multi eq)]

_Type_: **[Applications.Cms.WebModules](Applications.Cms.WebModules.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### WebSite

> The web site to which the module belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Applications.Cms.WebSites](Applications.Cms.WebSites.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.Cms.NewsWebModules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.Cms.NewsWebModules erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.Cms.NewsWebModules erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Cms_NewsWebModules?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Cms_NewsWebModules?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Cms_News_Web_Modules?$top=10>
