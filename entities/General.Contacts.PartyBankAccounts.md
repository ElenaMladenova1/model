# General.Contacts.PartyBankAccounts

The bank accounts of a party. Entity: Gen_Party_Bank_Accounts

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyBankAccounts.md#Id) | guid |  
| [BankAccountCode](General.Contacts.PartyBankAccounts.md#BankAccountCode) | string | The code of the account, usually the IBAN code. [Required] [Filter(eq;like)] 
| [BankAddress](General.Contacts.PartyBankAccounts.md#BankAddress) | [MultilanguageString](../data-types/MultilanguageString.md) (nullable) | The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments. 
| [BankBranchName](General.Contacts.PartyBankAccounts.md#BankBranchName) | [MultilanguageString](../data-types/MultilanguageString.md) (nullable) | The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments. 
| [BankCode](General.Contacts.PartyBankAccounts.md#BankCode) | string (nullable) | The code of the bank, usually the BIC code. [Filter(eq)] 
| [BankName](General.Contacts.PartyBankAccounts.md#BankName) | [MultilanguageString](../data-types/MultilanguageString.md) (nullable) | The full name of the bank. [Filter(like)] 
| [IsDefault](General.Contacts.PartyBankAccounts.md#IsDefault) | boolean | True if the this is the default account for the party. Only one default per party is allowed. [Required] [Default(false)] [Filter(eq)] 
| [Notes](General.Contacts.PartyBankAccounts.md#Notes) | string (nullable) | Notes for this PartyBankAccount. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](General.Contacts.PartyBankAccounts.md#Party) | [General.Contacts.Parties](General.Contacts.Parties.md) | The [Party](General.Contacts.PartyBankAccounts.md#Party) to which this PartyBankAccount belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### BankAccountCode

> The code of the account, usually the IBAN code. [Required] [Filter(eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### BankAddress

> The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments.

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md) (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### BankBranchName

> The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments.

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md) (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### BankCode

> The code of the bank, usually the BIC code. [Filter(eq)]

_Type_: **string (nullable)**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  

### BankName

> The full name of the bank. [Filter(like)]

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md) (nullable)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### IsDefault

> True if the this is the default account for the party. Only one default per party is allowed. [Required] [Default(false)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Notes

> Notes for this PartyBankAccount.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Party

> The [Party](General.Contacts.PartyBankAccounts.md#Party) to which this PartyBankAccount belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[General.Contacts.Parties](General.Contacts.Parties.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=General.Contacts.PartyBankAccounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=General.Contacts.PartyBankAccounts erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=General.Contacts.PartyBankAccounts erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Contacts_PartyBankAccounts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyBankAccounts?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Gen_Party_Bank_Accounts?$top=10>
