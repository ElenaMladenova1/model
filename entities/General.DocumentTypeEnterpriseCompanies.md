# General.DocumentTypeEnterpriseCompanies

Specifies the visibility (availability) of the document type for the different enterprise companies. Entity: Gen_Document_Type_Enterprise_Companies

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.DocumentTypeEnterpriseCompanies.md#Id) | guid |  

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](General.DocumentTypeEnterpriseCompanies.md#DocumentType) | [General.DocumentTypes](General.DocumentTypes.md) | The document type for which visibility (availability) is set. [Required] [Filter(multi eq)] [Owner] |
| [EnterpriseCompany](General.DocumentTypeEnterpriseCompanies.md#EnterpriseCompany) | [General.EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the current document type is visible (available). [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  


## Reference Details

### DocumentType

> The document type for which visibility (availability) is set. [Required] [Filter(multi eq)] [Owner]

_Type_: **[General.DocumentTypes](General.DocumentTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### EnterpriseCompany

> The enterprise company for which the current document type is visible (available). [Required] [Filter(multi eq)]

_Type_: **[General.EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=General.DocumentTypeEnterpriseCompanies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=General.DocumentTypeEnterpriseCompanies erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=General.DocumentTypeEnterpriseCompanies erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_DocumentTypeEnterpriseCompanies?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_DocumentTypeEnterpriseCompanies?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Gen_Document_Type_Enterprise_Companies?$top=10>
