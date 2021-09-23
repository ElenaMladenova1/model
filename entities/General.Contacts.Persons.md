---
uid: General.Contacts.Persons
---
# General.Contacts.Persons Entity

**Namespace:** [General.Contacts](General.Contacts.md)  
**Inherited From:** [General.Contacts.Parties](General.Contacts.Parties.md)  

Personal records. Requires related party record. Entity: Cm_Persons

## Default Visualization
Default Display Text Format:  
_{PartyName:T} : {PartyCode}_  
Default Search Member:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Contacts.Persons](General.Contacts.Persons.md)  
  * [Crm.SalesPersons](Crm.SalesPersons.md)  
  * [General.Contacts.CompanyEmployees](General.Contacts.CompanyEmployees.md)  
  * [Crm.Distributors](Crm.Distributors.md)  
  * [General.PartyApplicableLegislations](General.PartyApplicableLegislations.md)  
  * [General.PartyLocationNumbers](General.PartyLocationNumbers.md)  
  * [General.Contacts.ActivityTimeIntervals](General.Contacts.ActivityTimeIntervals.md)  
  * [General.Contacts.PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md)  
  * [General.Contacts.PartyBankAccounts](General.Contacts.PartyBankAccounts.md)  
  * [General.Contacts.PartyPictures](General.Contacts.PartyPictures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BirthDate](General.Contacts.Persons.md#birthdate) | datetime __nullable__ | Birth date. null means unknown. `Filter(ge;le)` 
| [City](General.Contacts.Persons.md#city) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | City from the legal registration address for the person. `Filter(like)` 
| [CreationTime](General.Contacts.Persons.md#creationtime) | datetime __nullable__ | Date and time when the Person was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](General.Contacts.Persons.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Person. `Filter(like)` `ReadOnly` 
| [FirstName](General.Contacts.Persons.md#firstname) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | First name of the person. `Filter(eq;like)` 
| [Gender](General.Contacts.Persons.md#gender) | [Gender](General.Contacts.Persons.md#gender) __nullable__ | Person gender. M=Male;F=Female;null=not known/not provided. `Filter(eq)` 
| [GLN](General.Contacts.Persons.md#gln) | string (13) __nullable__ | Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [Id](General.Contacts.Persons.md#id) | guid |  
| [IsActive](General.Contacts.Persons.md#isactive) | boolean | Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [LastName](General.Contacts.Persons.md#lastname) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | Last name of the person. `Filter(eq;like)` 
| [MiddleName](General.Contacts.Persons.md#middlename) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | Middle name of the person. `Filter(eq;like)` 
| [NationalNumber](General.Contacts.Persons.md#nationalnumber) | string (14) __nullable__ | Government assigned unique personal number. null means unknown. `Filter(eq;like)` 
| [Notes](General.Contacts.Persons.md#notes) | string (254) __nullable__ | Internal notes for the person. 
| [PartyCode](General.Contacts.Persons.md#partycode) | string (16) | The unique code of the party. `Required` `Filter(eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationTime](General.Contacts.Persons.md#partycreationtime) | datetime __nullable__ | Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationUser](General.Contacts.Persons.md#partycreationuser) | string (64) __nullable__ | Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyName](General.Contacts.Persons.md#partyname) | [MultilanguageString](../data-types.md#multilanguagestring) | The name of the party. `Required` `Filter(eq;like)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyNotes](General.Contacts.Persons.md#partynotes) | string (254) __nullable__ | Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyType](General.Contacts.Persons.md#partytype) | [PartyType](General.Contacts.Persons.md#partytype) | Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUniqueNumber](General.Contacts.Persons.md#partyuniquenumber) | string (16) __nullable__ | Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateTime](General.Contacts.Persons.md#partyupdatetime) | datetime __nullable__ | Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateUser](General.Contacts.Persons.md#partyupdateuser) | string (64) __nullable__ | Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PassportIssuingDate](General.Contacts.Persons.md#passportissuingdate) | datetime __nullable__ | Date of issuing the passport. null means unknown. `Filter(ge;le)` 
| [PassportNumber](General.Contacts.Persons.md#passportnumber) | string (14) __nullable__ | Current passport number. null means unknown. `Filter(eq)` 
| [Title](General.Contacts.Persons.md#title) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The persons title. It may be one of the standard titles - Mr., Mrs., etc., but it can also contains professional or academic qualification. 
| [UpdateTime](General.Contacts.Persons.md#updatetime) | datetime __nullable__ | Date and time when the Person was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](General.Contacts.Persons.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Person. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](General.Contacts.Persons.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Area](General.Contacts.Persons.md#area) | [Areas](General.Geography.Areas.md) (nullable) | The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [DefaultProductCodingSystem](General.Contacts.Persons.md#defaultproductcodingsystem) | [CodingSystems](General.Products.CodingSystems.md) (nullable) | When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Nationality](General.Contacts.Persons.md#nationality) | [Countries](General.Geography.Countries.md) (nullable) | Person's nationality. null means the default (same as enterprise) nationality. `Filter(multi eq)` |
| [ParentParty](General.Contacts.Persons.md#parentparty) | [Parties](General.Contacts.Parties.md) (nullable) | Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ActivityTimeIntervals | [ActivityTimeIntervals](General.Contacts.ActivityTimeIntervals.md) | List of `ActivityTimeInterval`(General.Contacts.ActivityTimeIntervals.md) child objects, based on the `General.Contacts.ActivityTimeInterval.Party`(General.Contacts.ActivityTimeIntervals.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| ApplicableLegislations | [PartyApplicableLegislations](General.PartyApplicableLegislations.md) | List of `PartyApplicable<br />Legislation`(General.PartyApplicable<br />Legislations.md) child objects, based on the `General.PartyApplicableLegislation.Party`(General.PartyApplicable<br />Legislations.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| BankAccounts | [PartyBankAccounts](General.Contacts.PartyBankAccounts.md) | List of `PartyBankAccount`(General.Contacts.PartyBankAccounts.md) child objects, based on the `General.Contacts.PartyBankAccount.Party`(General.Contacts.PartyBankAccounts.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| CompanyEmployees | [CompanyEmployees](General.Contacts.CompanyEmployees.md) | List of `CompanyEmployee`(General.Contacts.CompanyEmployees.md) child objects, based on the `General.Contacts.CompanyEmployee.Person`(General.Contacts.CompanyEmployees.md#person) back reference 
| ContactMechanisms | [PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md) | List of `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md) child objects, based on the `General.Contacts.PartyContactMechanism.Party`(General.Contacts.PartyContactMechanisms.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Distributors | [Distributors](Crm.Distributors.md) | List of `Distributor`(Crm.Distributors.md) child objects, based on the `Crm.Distributor.Party`(Crm.Distributors.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| LocationNumbers | [PartyLocationNumbers](General.PartyLocationNumbers.md) | List of `PartyLocationNumber`(General.PartyLocationNumbers.md) child objects, based on the `General.PartyLocationNumber.Party`(General.PartyLocationNumbers.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Pictures | [PartyPictures](General.Contacts.PartyPictures.md) | List of `PartyPicture`(General.Contacts.PartyPictures.md) child objects, based on the `General.Contacts.PartyPicture.Party`(General.Contacts.PartyPictures.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| SalesPersons | [SalesPersons](Crm.SalesPersons.md) | List of `SalesPerson`(Crm.SalesPersons.md) child objects, based on the `Crm.SalesPerson.Person`(Crm.SalesPersons.md#person) back reference 


## Attribute Details

### BirthDate

Birth date. null means unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### City

City from the legal registration address for the person. `Filter(like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### CreationTime

Date and time when the Person was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### CreationUser

Login name of the user, who created the Person. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### FirstName

First name of the person. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Gender

Person gender. M=Male;F=Female;null=not known/not provided. `Filter(eq)`

_Type_: **[Gender](General.Contacts.Persons.md#gender) __nullable__**  
Allowed values for the `Gender`(General.Contacts.Persons.md#gender) data attribute  
_Allowed Values (General.Contacts.PersonsRepository.Gender Enum Members)_  

| Value | Description |
| ---- | --- |
| Female | Female value. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Female' |
| Male | Male value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Male' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### GLN

Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (13) __nullable__**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **13**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsActive

Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### LastName

Last name of the person. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### MiddleName

Middle name of the person. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### NationalNumber

Government assigned unique personal number. null means unknown. `Filter(eq;like)`

_Type_: **string (14) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **14**  

### Notes

Internal notes for the person.

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### PartyCode

The unique code of the party. `Required` `Filter(eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (16)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  

### PartyCreationTime

Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### PartyCreationUser

Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (64) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### PartyName

The name of the party. `Required` `Filter(eq;like)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  

### PartyNotes

Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### PartyType

Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[PartyType](General.Contacts.Persons.md#partytype)**  
Allowed values for the PartyType data attribute  
_Allowed Values (General.Contacts.PartiesRepository.PartyType Enum Members)_  

| Value | Description |
| ---- | --- |
| Company | Company value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Company' |
| CompanyLocation | CompanyLocation value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CompanyLocation' |
| Person | Person value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Person' |
| Store | Store value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Store' |
| CompanyDivision | CompanyDivision value. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'CompanyDivision' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Person**  

### PartyUniqueNumber

Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (16) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  

### PartyUpdateTime

Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### PartyUpdateUser

Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **string (64) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### PassportIssuingDate

Date of issuing the passport. null means unknown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### PassportNumber

Current passport number. null means unknown. `Filter(eq)`

_Type_: **string (14) __nullable__**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **14**  

### Title

The persons title. It may be one of the standard titles - Mr., Mrs., etc., but it can also contains professional or academic qualification.

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### UpdateTime

Date and time when the Person was last updated. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### UpdateUser

Login name of the user, who last updated the Person. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  


## Reference Details

### AdministrativeRegion

The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Area

The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[Areas](General.Geography.Areas.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### DefaultProductCodingSystem

When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[CodingSystems](General.Products.CodingSystems.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Nationality

Person's nationality. null means the default (same as enterprise) nationality. `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### ParentParty

Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list limit=1000 erp.entity=General.Contacts.Persons erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.Persons erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Contacts_Persons?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Contacts_Persons?$top=10>

