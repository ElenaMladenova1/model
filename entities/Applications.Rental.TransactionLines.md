# Applications.Rental.TransactionLines

Contains all transactions of Record of Handover / Handing-Over Record lines. Entity: Rent_Transaction_Lines

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Rental.TransactionLines.md#Id) | guid |  
| [Notes](Applications.Rental.TransactionLines.md#Notes) | string (nullable) | Notes. 
| [TransactionTimestamp](Applications.Rental.TransactionLines.md#TransactionTimestamp) | datetime | Transaction Timestamp. [Required] [Filter(multi eq;ge;le)] 
| [TransactionType](Applications.Rental.TransactionLines.md#TransactionType) | [Applications.Rental.TransactionLinesRepository.TransactionType](Applications.Rental.TransactionLines.md#TransactionType) | Transaction Type. [Required] [Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LeaseContract](Applications.Rental.TransactionLines.md#LeaseContract) | [Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md) | Lease Contract. [Required] [Filter(multi eq)] |
| [LesseeCustomer](Applications.Rental.TransactionLines.md#LesseeCustomer) | [Crm.Customers](Crm.Customers.md) | Lessee Customer. [Required] [Filter(multi eq)] |
| [RentTransaction](Applications.Rental.TransactionLines.md#RentTransaction) | [Applications.Rental.Transactions](Applications.Rental.Transactions.md) | The [Transaction](Applications.Rental.Transactions.md) to which this TransactionLine belongs. [Required] [Filter(multi eq)] [Owner] |
| [RentalAsset](Applications.Rental.TransactionLines.md#RentalAsset) | [Applications.Rental.Assets](Applications.Rental.Assets.md) | Rental asset. [Required] [Filter(multi eq)] |


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Notes

> Notes.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TransactionTimestamp

> Transaction Timestamp. [Required] [Filter(multi eq;ge;le)]

_Type_: **datetime**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  

### TransactionType

> Transaction Type. [Required] [Filter(eq;like)]

_Type_: **[Applications.Rental.TransactionLinesRepository.TransactionType](Applications.Rental.TransactionLines.md#TransactionType)**  
Allowed values for the [TransactionType](Applications.Rental.TransactionLines.md#TransactionType) data attribute  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| Deliver | Deliver value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Deliver' |
| Receive | Receive value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Receive' |
| WriteOffNotReturned | WriteOffNotReturned value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'WriteOffNotReturned' |
| StatusReport | StatusReport value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'StatusReport' |

_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


## Reference Details

### LeaseContract

> Lease Contract. [Required] [Filter(multi eq)]

_Type_: **[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### LesseeCustomer

> Lessee Customer. [Required] [Filter(multi eq)]

_Type_: **[Crm.Customers](Crm.Customers.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### RentTransaction

> The [Transaction](Applications.Rental.Transactions.md) to which this TransactionLine belongs. [Required] [Filter(multi eq)] [Owner]

_Type_: **[Applications.Rental.Transactions](Applications.Rental.Transactions.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### RentalAsset

> Rental asset. [Required] [Filter(multi eq)]

_Type_: **[Applications.Rental.Assets](Applications.Rental.Assets.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Applications.Rental.TransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Applications.Rental.TransactionLines erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Applications.Rental.TransactionLines erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Rental_TransactionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Rental_TransactionLines?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Rent_Transaction_Lines?$top=10>
