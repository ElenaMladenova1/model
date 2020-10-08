# General.SequenceGenerators

Contains one or more sequence generators for each sequence. Many sequence generators for one sequence are used when the generators must be selected conditionally or when more generators are needed for parallel numbering. Entity: Gen_Sequence_Generators

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.SequenceGenerators.md#Id) | guid |  
| [AllowExplicitNumbering](General.SequenceGenerators.md#AllowExplicitNumbering) | boolean | Allows to assign numbers explicitely regardless of the Next_Value of the generator (Next_Value is updated if needed). [Required] [Default(false)] 
| [NextValue](General.SequenceGenerators.md#NextValue) | string | The next number that will be issued by the sequence. [Required] [Default("0000000001")] 
| [SequencePriority](General.SequenceGenerators.md#SequencePriority) | int32 | The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True. [Required] [Default(1)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](General.SequenceGenerators.md#EnterpriseCompany) | [General.EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this SequenceGenerator applies. [Required] [Filter(multi eq)] |
| [EnterpriseCompanyLocation](General.SequenceGenerators.md#EnterpriseCompanyLocation) | [General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. [Filter(multi eq)] |
| [ResponsiblePerson](General.SequenceGenerators.md#ResponsiblePerson) | [General.Contacts.Persons](General.Contacts.Persons.md) (nullable) | If specified then the generator is designated for use only in documents with that Responsible_Person_Id. [Filter(multi eq)] |
| [Sequence](General.SequenceGenerators.md#Sequence) | [General.Sequences](General.Sequences.md) | The [Sequence](General.SequenceGenerators.md#Sequence) to which this SequenceGenerator belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### AllowExplicitNumbering

> Allows to assign numbers explicitely regardless of the Next_Value of the generator (Next_Value is updated if needed). [Required] [Default(false)]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### NextValue

> The next number that will be issued by the sequence. [Required] [Default("0000000001")]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0000000001**  

### SequencePriority

> The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True. [Required] [Default(1)]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  


## Reference Details

### EnterpriseCompany

> The Enterprise Company to which this SequenceGenerator applies. [Required] [Filter(multi eq)]

_Type_: **[General.EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### EnterpriseCompanyLocation

> The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. [Filter(multi eq)]

_Type_: **[General.Contacts.CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### ResponsiblePerson

> If specified then the generator is designated for use only in documents with that Responsible_Person_Id. [Filter(multi eq)]

_Type_: **[General.Contacts.Persons](General.Contacts.Persons.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Sequence

> The [Sequence](General.SequenceGenerators.md#Sequence) to which this SequenceGenerator belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[General.Sequences](General.Sequences.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=General.SequenceGenerators erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=General.SequenceGenerators erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=General.SequenceGenerators erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_SequenceGenerators?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_SequenceGenerators?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Gen_Sequence_Generators?$top=10>
