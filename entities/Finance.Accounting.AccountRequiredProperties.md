# Finance.Accounting.AccountRequiredProperties

Defines the required properties for new vouchers, for each account. Entity: Acc_Account_Required_Properties

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.AccountRequiredProperties.md#Id) | guid |  
| [KeyOrder](Finance.Accounting.AccountRequiredProperties.md#KeyOrder) | int32 | The key order determines in which order the values and descriptions of the properties will form the item (grouping) key and description. [Required] 
| [KeyProperty](Finance.Accounting.AccountRequiredProperties.md#KeyProperty) | boolean | Key properties particiate in forming the grouping key, which is the smallest unit of calculation for account balance. Non-key properties simply serve for comment and clarification purposes. [Required] [Default(true)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountRequiredProperties.md#Account) | [Finance.Accounting.Accounts](Finance.Accounting.Accounts.md) | The [Account](Finance.Accounting.AccountRequiredProperties.md#Account) to which this AccountRequiredProperty belongs. [Required] [Filter(multi eq)] [Owner] |
| [Property](Finance.Accounting.AccountRequiredProperties.md#Property) | [General.CustomProperties](General.CustomProperties.md) | A property of type (Entity_Name = Account Voucher Line) for which the user can specify value when entering accounting vouchers. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### KeyOrder

> The key order determines in which order the values and descriptions of the properties will form the item (grouping) key and description. [Required]

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`(obj.Account.RequiredProperties.Select(c => c.KeyOrder).DefaultIfEmpty(0).Max() + 10)`

_Front-End Recalc Expressions:_  
`(obj.Account.RequiredProperties.Select(c => c.KeyOrder).DefaultIfEmpty(0).Max() + 10)`
### KeyProperty

> Key properties particiate in forming the grouping key, which is the smallest unit of calculation for account balance. Non-key properties simply serve for comment and clarification purposes. [Required] [Default(true)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  


## Reference Details

### Account

> The [Account](Finance.Accounting.AccountRequiredProperties.md#Account) to which this AccountRequiredProperty belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Finance.Accounting.Accounts](Finance.Accounting.Accounts.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Property

> A property of type (Entity_Name = Account Voucher Line) for which the user can specify value when entering accounting vouchers. [Required] [Filter(multi eq)]

_Type_: **[General.CustomProperties](General.CustomProperties.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Finance.Accounting.AccountRequiredProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Accounting.AccountRequiredProperties erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Finance.Accounting.AccountRequiredProperties erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Accounting_AccountRequiredProperties?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountRequiredProperties?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Acc_Account_Required_Properties?$top=10>
