---
uid: Finance.Vat.DeclarationLines
---
# Finance.Vat.DeclarationLines Entity

**Namespace:** [Finance.Vat](Finance.Vat.md)  

Contains the VAT declaration lines for declaration, issued by the enterprise company, according to the eligible legislation. Entity: VAT_Declaration_Lines (Introduced in version 22.1.4.22)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {Declaration.DocumentNo} {Declaration.DocumentType.TypeName:T}_  
Default Search Members:  
_Declaration.DocumentNo_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Vat.Declarations](Finance.Vat.Declarations.md)  
Aggregate Root:  
[Finance.Vat.Declarations](Finance.Vat.Declarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountBase](Finance.Vat.DeclarationLines.md#amountbase) | decimal (14, 2) | Declared value in base currency. `Required` `Default(0)` `Filter(eq;ge;le)` 
| [DisplayText](Finance.Vat.DeclarationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Vat.DeclarationLines.md#id) | guid |  
| [LineNo](Finance.Vat.DeclarationLines.md#lineno) | int32 | Consecutive line number within the document. `Required` 
| [Notes](Finance.Vat.DeclarationLines.md#notes) | string (max) __nullable__ | Notes for this DeclarationLine. 
| [ObjectVersion](Finance.Vat.DeclarationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxType](Finance.Vat.DeclarationLines.md#boxtype) | [BoxTypes](Finance.Vat.BoxTypes.md) | Type of box in VAT declaration. . `Required` `Filter(multi eq)` |
| [Declaration](Finance.Vat.DeclarationLines.md#declaration) | [Declarations](Finance.Vat.Declarations.md) | The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Finance.Vat.DeclarationLines.md#document) | [Declarations](Finance.Vat.Declarations.md) | The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` |


## Attribute Details

### AmountBase

Declared value in base currency. `Required` `Default(0)` `Filter(eq;ge;le)`

_Type_: **decimal (14, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineNo

Consecutive line number within the document. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.Declaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Declaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this DeclarationLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### BoxType

Type of box in VAT declaration. . `Required` `Filter(multi eq)`

_Type_: **[BoxTypes](Finance.Vat.BoxTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### Declaration

The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Declarations](Finance.Vat.Declarations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### Document

The <see cref="Declaration"/> to which this DeclarationLine belongs. `Required` `Filter(multi eq)`

_Type_: **[Declarations](Finance.Vat.Declarations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


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


### CreateNotification

Creates a notification a sends a real time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The subject.  
    _Type_: string  



## Business Rules

[!list limit=1000 erp.entity=Finance.Vat.DeclarationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Vat.DeclarationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Vat_DeclarationLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Vat_DeclarationLines?$top=10>

