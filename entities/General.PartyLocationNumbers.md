# General.PartyLocationNumbers

Location numbers for a party. Depending on the partner with which we are doing an exchange, our location number might be different. Entity: Gen_Party_Location_Numbers (Introduced in version 19.1.100.0)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.PartyLocationNumbers.md#Id) | guid |  
| [LocationCodingSystem](General.PartyLocationNumbers.md#LocationCodingSystem) | [General.PartyLocationNumbersRepository.LocationCodingSystem](General.PartyLocationNumbers.md#LocationCodingSystem) | The coding system for which we are defining the location number. [Required] [Default("GLN")] [Filter(multi eq)] 
| [LocationNumber](General.PartyLocationNumbers.md#LocationNumber) | string | The location number of Party. [Required] [Filter(multi eq;like)] [ORD] 
| [PartnerLocationNumber](General.PartyLocationNumbers.md#PartnerLocationNumber) | string (nullable) | The location number of the partner party for which we define the main Party location number. The location number of the main Party might be different depending on the location number of the partner party. null means that the location number is not dependent on the partner location number. [Filter(multi eq)] 
| [Significance](General.PartyLocationNumbers.md#Significance) | int32 | Order of significance of the location number within the main Party. If there are multiple location numbers, only the most significant is used. 0 is the least significant and higher numbers indicate higher significance. [Required] [Default(0)] [Filter(multi eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PartnerParty](General.PartyLocationNumbers.md#PartnerParty) | [General.Contacts.Parties](General.Contacts.Parties.md) (nullable) | The party with which we are doing exchange. Depending on the Partner Party, the main Party might have different location number. null means that the location number is not dependent on the Partner Party. [Filter(multi eq)] |
| [Party](General.PartyLocationNumbers.md#Party) | [General.Contacts.Parties](General.Contacts.Parties.md) | The party for which we are defining the location number. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### LocationCodingSystem

> The coding system for which we are defining the location number. [Required] [Default("GLN")] [Filter(multi eq)]

_Type_: **[General.PartyLocationNumbersRepository.LocationCodingSystem](General.PartyLocationNumbers.md#LocationCodingSystem)**  
Allowed values for the [LocationCodingSystem](General.PartyLocationNumbers.md#LocationCodingSystem) data attribute  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| GLN | GS1 Global Location Number (GLN). Stored as 'GLN'. <br /> _Database Value:_ 'GLN' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'GLN' |
| Internal | Internal users have access to internal and external content.. Stored as 'INT'. <br /> _Database Value:_ 'INT' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Internal' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **GLN**  

### LocationNumber

> The location number of Party. [Required] [Filter(multi eq;like)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  

### PartnerLocationNumber

> The location number of the partner party for which we define the main Party location number. The location number of the main Party might be different depending on the location number of the partner party. null means that the location number is not dependent on the partner location number. [Filter(multi eq)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Significance

> Order of significance of the location number within the main Party. If there are multiple location numbers, only the most significant is used. 0 is the least significant and higher numbers indicate higher significance. [Required] [Default(0)] [Filter(multi eq;ge;le)]

_Type_: **int32**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### PartnerParty

> The party with which we are doing exchange. Depending on the Partner Party, the main Party might have different location number. null means that the location number is not dependent on the Partner Party. [Filter(multi eq)]

_Type_: **[General.Contacts.Parties](General.Contacts.Parties.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Party

> The party for which we are defining the location number. [Required] [Filter(multi eq)] [Owner]

_Type_: **[General.Contacts.Parties](General.Contacts.Parties.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=General.PartyLocationNumbers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=General.PartyLocationNumbers erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=General.PartyLocationNumbers erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_PartyLocationNumbers?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_PartyLocationNumbers?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Gen_Party_Location_Numbers?$top=10>
