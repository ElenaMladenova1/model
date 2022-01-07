---
uid: General.SequenceGenerators
---
# General.SequenceGenerators Entity

**Namespace:** [General](General.md)  

Contains one or more sequence generators for each sequence. Many sequence generators for one sequence are used when the generators must be selected conditionally or when more generators are needed for parallel numbering. Entity: Gen_Sequence_Generators

## Default Visualization
Default Display Text Format:  
_{Sequence.Name}_  
Default Search Members:  
_Sequence.Name_  
Name Data Member:  
_Sequence.Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Sequences](General.Sequences.md)  
Aggregate Root:  
[General.Sequences](General.Sequences.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowExplicitNumbering](General.SequenceGenerators.md#allowexplicitnumbering) | boolean | Allows to assign numbers explicitely regardless of the Next_Value of the generator (Next_Value is updated if needed). `Required` `Default(false)` 
| [DisplayText](General.SequenceGenerators.md#displaytext) | string |  
| [Id](General.SequenceGenerators.md#id) | guid |  
| [NextValue](General.SequenceGenerators.md#nextvalue) | string (16) | The next number that will be issued by the sequence. `Required` `Default("0000000001")` 
| [ObjectVersion](General.SequenceGenerators.md#objectversion) | int32 |  
| [SequencePriority](General.SequenceGenerators.md#sequencepriority) | int32 | The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](General.SequenceGenerators.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this SequenceGenerator applies. `Required` `Filter(multi eq)` |
| [EnterpriseCompanyLocation](General.SequenceGenerators.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. `Filter(multi eq)` |
| [ResponsiblePerson](General.SequenceGenerators.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | If specified then the generator is designated for use only in documents with that Responsible_Person_Id. `Filter(multi eq)` |
| [Sequence](General.SequenceGenerators.md#sequence) | [Sequences](General.Sequences.md) | The <see cref="Sequence"/> to which this SequenceGenerator belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### AllowExplicitNumbering

Allows to assign numbers explicitely regardless of the Next_Value of the generator (Next_Value is updated if needed). `Required` `Default(false)`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### DisplayText

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### NextValue

The next number that will be issued by the sequence. `Required` `Default("0000000001")`

_Type_: **string (16)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Default Value_: **0000000001**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### SequencePriority

The priority in which the sequence is used, compared to other similar sequences. Used only for sequences, for which Simultaneous Transactions=True. `Required` `Default(1)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  


## Reference Details

### EnterpriseCompany

The Enterprise Company to which this SequenceGenerator applies. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this SequenceGenerator applies, or null if it is for all enterprise company locations. `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### ResponsiblePerson

If specified then the generator is designated for use only in documents with that Responsible_Person_Id. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Sequence

The <see cref="Sequence"/> to which this SequenceGenerator belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Sequences](General.Sequences.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  



## Business Rules

[!list limit=1000 erp.entity=General.SequenceGenerators erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.SequenceGenerators erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_SequenceGenerators?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_SequenceGenerators?$top=10>

