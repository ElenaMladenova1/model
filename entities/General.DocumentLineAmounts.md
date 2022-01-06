---
uid: General.DocumentLineAmounts
---
# General.DocumentLineAmounts Entity

**Namespace:** [General](General.md)  

Specifies user-defined input percentages by lines for the document amounts. Entity: Gen_Document_Line_Amounts

## Default Visualization
Default Display Text Format:  
_{Document.EntityName}_  
Default Search Members:  
_Document.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents](General.Documents.md)  
Aggregate Root:  
[General.Documents](General.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentLineId](General.DocumentLineAmounts.md#documentlineid) | guid | The line for which the distribution pattern is specified. `Required` `Filter(multi eq)` 
| [Id](General.DocumentLineAmounts.md#id) | guid |  
| [LinePercent](General.DocumentLineAmounts.md#linepercent) | decimal (14, 6) | The percent of the additional amount which should be distributed over the current line. `Required` `Default(0)` 
| [ObjectVersion](General.DocumentLineAmounts.md#objectversion) | int32 |  

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.DocumentLineAmounts.md#document) | [Documents](General.Documents.md) | The <see cref="Document"/> to which this DocumentLineAmount belongs. `Required` `Filter(multi eq)` `Owner` |
| [DocumentAmountType](General.DocumentLineAmounts.md#documentamounttype) | [DocumentAmountTypes](General.DocumentAmountTypes.md) | The type of amount for which the distribution pattern is specified. `Required` `Filter(multi eq)` |
| [Product](General.DocumentLineAmounts.md#product) | [Products](General.Products.Products.md) | The product for which the distribution is specified. It is also the product, specified in the document line, but is duplicated here for integrity purposes. `Required` `Filter(multi eq)` |
| [ReferencedDocument](General.DocumentLineAmounts.md#referenceddocument) | [Documents](General.Documents.md) (nullable) | When not null, specifies that this distribution is specified for a referenced document (not the document for which the amount is calculated). `Filter(multi eq)` |


## Attribute Details

### DocumentLineId

The line for which the distribution pattern is specified. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LinePercent

The percent of the additional amount which should be distributed over the current line. `Required` `Default(0)`

_Type_: **decimal (14, 6)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### Document

The <see cref="Document"/> to which this DocumentLineAmount belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Documents](General.Documents.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### DocumentAmountType

The type of amount for which the distribution pattern is specified. `Required` `Filter(multi eq)`

_Type_: **[DocumentAmountTypes](General.DocumentAmountTypes.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### Product

The product for which the distribution is specified. It is also the product, specified in the document line, but is duplicated here for integrity purposes. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### ReferencedDocument

When not null, specifies that this distribution is specified for a referenced document (not the document for which the amount is calculated). `Filter(multi eq)`

_Type_: **[Documents](General.Documents.md) (nullable)**  
_Indexed_: **True**  
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



## Business Rules

[!list limit=1000 erp.entity=General.DocumentLineAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.DocumentLineAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_DocumentLineAmounts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_DocumentLineAmounts?$top=10>

