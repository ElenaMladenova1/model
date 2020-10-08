# Finance.Payments.PaymentTransactionLines

Contains the distibution of the payments' amounts among the source payment orders. Entity: Cash_Payment_Transaction_Lines

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Payments.PaymentTransactionLines.md#Id) | guid |  
| [AllowOverpayment](Finance.Payments.PaymentTransactionLines.md#AllowOverpayment) | boolean | True-Allows overpayment for the payment order; false=Does not allow (default). [Required] [Default(false)] 
| [Amount](Finance.Payments.PaymentTransactionLines.md#Amount) | [Amount](../data-types/Amount.md) | The part of the total payed amount by the transaction, that is distributed to the specified payment order. [Currency: PaymentTransaction.TotalAmountCurrency] [Required] [Default(0)] 
| [CoveredOrderAmount](Finance.Payments.PaymentTransactionLines.md#CoveredOrderAmount) | [Amount](../data-types/Amount.md) | The part of the original payment order amount, that is covered by this transaction line. [Currency: PaymentOrder.TotalAmountCurrency] [Required] [Default(0)] 
| [Notes](Finance.Payments.PaymentTransactionLines.md#Notes) | string (nullable) | Notes for this PaymentTransactionLine. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PaymentOrder](Finance.Payments.PaymentTransactionLines.md#PaymentOrder) | [Finance.Payments.PaymentOrders](Finance.Payments.PaymentOrders.md) | The payment order, that is covered by this transaction amount distribution (tr.line). [Required] [Filter(multi eq)] |
| [PaymentTransaction](Finance.Payments.PaymentTransactionLines.md#PaymentTransaction) | [Finance.Payments.PaymentTransactions](Finance.Payments.PaymentTransactions.md) | The [PaymentTransaction](Finance.Payments.PaymentTransactionLines.md#PaymentTransaction) to which this PaymentTransactionLine belongs. [Required] [Filter(multi eq)] [Owner] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### AllowOverpayment

> True-Allows overpayment for the payment order; false=Does not allow (default). [Required] [Default(false)]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Amount

> The part of the total payed amount by the transaction, that is distributed to the specified payment order. [Currency: PaymentTransaction.TotalAmountCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

_Front-End Recalc Expressions:_  
`obj.CoveredOrderAmount.ConvertTo(obj.PaymentTransaction.TotalAmountCurrency, obj.PaymentTransaction.CurrencyDirectory)`
### CoveredOrderAmount

> The part of the original payment order amount, that is covered by this transaction line. [Currency: PaymentOrder.TotalAmountCurrency] [Required] [Default(0)]

_Type_: **[Amount](../data-types/Amount.md)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

_Front-End Recalc Expressions:_  
`obj.Amount.ConvertTo(obj.PaymentOrder.TotalAmountCurrency, obj.PaymentTransaction.CurrencyDirectory)`
### Notes

> Notes for this PaymentTransactionLine.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### PaymentOrder

> The payment order, that is covered by this transaction amount distribution (tr.line). [Required] [Filter(multi eq)]

_Type_: **[Finance.Payments.PaymentOrders](Finance.Payments.PaymentOrders.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### PaymentTransaction

> The [PaymentTransaction](Finance.Payments.PaymentTransactionLines.md#PaymentTransaction) to which this PaymentTransactionLine belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Finance.Payments.PaymentTransactions](Finance.Payments.PaymentTransactions.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Finance.Payments.PaymentTransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Payments.PaymentTransactionLines erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Finance.Payments.PaymentTransactionLines erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Payments_PaymentTransactionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Payments_PaymentTransactionLines?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Cash_Payment_Transaction_Lines?$top=10>
