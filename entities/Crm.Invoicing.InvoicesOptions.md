# Crm.Invoicing.InvoicesOptions

Default options for user document types for Invoices. Entity: Crm_Invoices_Options

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Invoicing.InvoicesOptions.md#Id) | guid |  
| [CreatesVATEntries](Crm.Invoicing.InvoicesOptions.md#CreatesVATEntries) | boolean | Specifies whether the invoices of the current type create entries in the VAT ledges. If is used, for instance, to determine if null VAT entry should be automatically created when the invoice is voided. [Required] [Default(true)] 
| [SignRestriction](Crm.Invoicing.InvoicesOptions.md#SignRestriction) | [General.SignRestriction](Crm.Invoicing.InvoicesOptions.md#SignRestriction) | Restricts the sign of the line amounts of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. [Required] [Default(0)] 
| [TotalAmountSignRestriction](Crm.Invoicing.InvoicesOptions.md#TotalAmountSignRestriction) | [General.SignRestriction](Crm.Invoicing.InvoicesOptions.md#TotalAmountSignRestriction) | Restricts the sign of the total amount (amount to pay) of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. [Required] [Default(0)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultDealType](Crm.Invoicing.InvoicesOptions.md#DefaultDealType) | [Finance.Vat.DealTypes](Finance.Vat.DealTypes.md) (nullable) | When not null, specifies default VAT deal type. [Filter(multi eq)] |
| [DocumentType](Crm.Invoicing.InvoicesOptions.md#DocumentType) | [General.DocumentTypes](General.DocumentTypes.md) | The document type for which the invoice option applies. [Required] [Filter(multi eq)] [Owner] |
| [VATDeviationDocumentAmountType](Crm.Invoicing.InvoicesOptions.md#VATDeviationDocumentAmountType) | [General.DocumentAmountTypes](General.DocumentAmountTypes.md) (nullable) | Document amount that contains the difference between the total amount of the invoice formed by unit prices with VAT and the amount formed by unit prices without VAT. [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### CreatesVATEntries

> Specifies whether the invoices of the current type create entries in the VAT ledges. If is used, for instance, to determine if null VAT entry should be automatically created when the invoice is voided. [Required] [Default(true)]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### SignRestriction

> Restricts the sign of the line amounts of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. [Required] [Default(0)]

_Type_: **[General.SignRestriction](Crm.Invoicing.InvoicesOptions.md#SignRestriction)**  
Generic enum type for SignRestriction properties  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'AllowOnlyNegative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### TotalAmountSignRestriction

> Restricts the sign of the total amount (amount to pay) of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. [Required] [Default(0)]

_Type_: **[General.SignRestriction](Crm.Invoicing.InvoicesOptions.md#TotalAmountSignRestriction)**  
Generic enum type for SignRestriction properties  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'AllowOnlyNegative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### DefaultDealType

> When not null, specifies default VAT deal type. [Filter(multi eq)]

_Type_: **[Finance.Vat.DealTypes](Finance.Vat.DealTypes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### DocumentType

> The document type for which the invoice option applies. [Required] [Filter(multi eq)] [Owner]

_Type_: **[General.DocumentTypes](General.DocumentTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### VATDeviationDocumentAmountType

> Document amount that contains the difference between the total amount of the invoice formed by unit prices with VAT and the amount formed by unit prices without VAT. [Filter(multi eq)]

_Type_: **[General.DocumentAmountTypes](General.DocumentAmountTypes.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Crm.Invoicing.InvoicesOptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Crm.Invoicing.InvoicesOptions erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Crm.Invoicing.InvoicesOptions erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoicesOptions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoicesOptions?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Invoices_Options?$top=10>
