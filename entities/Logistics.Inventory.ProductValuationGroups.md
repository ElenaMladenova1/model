---
uid: Logistics.Inventory.ProductValuationGroups
---
# Logistics.Inventory.ProductValuationGroups Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Contains the available valuation groups for products. They are used in reconciliations, where all pluses and minuses within a valuation group are allowed to balance each other without fiscal effects. Without valuation groups, each product is balanced for itself and taxes are calculated for each surplus. Entity: Inv_Product_Valuation_Groups

## Default Visualization
Default Display Text Format:  
_{ValuationGroupName:T}_  
Default Search Members:  
_ValuationGroupCode; ValuationGroupName_  
Code Data Member:  
_ValuationGroupCode_  
Name Data Member:  
_ValuationGroupName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.ProductValuationGroups](Logistics.Inventory.ProductValuationGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Logistics.Inventory.ProductValuationGroups.md#description) | string (254) __nullable__ | The description of this ProductValuationGroup. `Filter(like)` 
| [DisplayText](Logistics.Inventory.ProductValuationGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Inventory.ProductValuationGroups.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.ProductValuationGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ValuationGroupCode](Logistics.Inventory.ProductValuationGroups.md#valuationgroupcode) | string (64) | The unique code of the product valuation group. `Required` `Filter(eq;like)` `ORD` 
| [ValuationGroupName](Logistics.Inventory.ProductValuationGroups.md#valuationgroupname) | [MultilanguageString](../data-types.md#multilanguagestring) | The name of the product valuation group. `Required` `Filter(eq;like)` 


## Attribute Details

### Description

The description of this ProductValuationGroup. `Filter(like)`

_Type_: **string (254) __nullable__**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ValuationGroupCode

The unique code of the product valuation group. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  

### ValuationGroupName

The name of the product valuation group. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


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

[!list limit=1000 erp.entity=Logistics.Inventory.ProductValuationGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.ProductValuationGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Inventory_ProductValuationGroups?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ProductValuationGroups?$top=10>

