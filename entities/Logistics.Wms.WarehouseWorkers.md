---
uid: Logistics.Wms.WarehouseWorkers
---
# Logistics.Wms.WarehouseWorkers Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Human or robot worker, which can execute warehouse tasks. Entity: Wms_Warehouse_Workers (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
Aggregate Root:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActiveFrom](Logistics.Wms.WarehouseWorkers.md#activefrom) | date | The date, from which the worker record has become active in the warehouse. `Required` `Default(Today)` `Filter(eq;ge;le)` 
| [ActiveTo](Logistics.Wms.WarehouseWorkers.md#activeto) | date __nullable__ | The date of termination of the activity of the worker in the warehouse. Can be null for workers, which are still active and do not have previous terminations. `Filter(eq;ge;le)` 
| [DisplayText](Logistics.Wms.WarehouseWorkers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Wms.WarehouseWorkers.md#id) | guid |  
| [IsActive](Logistics.Wms.WarehouseWorkers.md#isactive) | boolean | Specifies whether the worker is active and can execute new warehouse tasks. `Required` `Default(true)` `Filter(eq)` 
| [Name](Logistics.Wms.WarehouseWorkers.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | Name of the worker (multi-language). `Required` `Filter(multi eq;like)` 
| [Notes](Logistics.Wms.WarehouseWorkers.md#notes) | string (max) __nullable__ | Notes for this WarehouseWorker. 
| [ObjectVersion](Logistics.Wms.WarehouseWorkers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Person](Logistics.Wms.WarehouseWorkers.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The definition of the person, when the worker is human worker. null means that the person is unknown or the worker is non-person. `Filter(multi eq)` |
| [Warehouse](Logistics.Wms.WarehouseWorkers.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse, where the worker works. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ActiveFrom

The date, from which the worker record has become active in the warehouse. `Required` `Default(Today)` `Filter(eq;ge;le)`

_Type_: **date**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  

### ActiveTo

The date of termination of the activity of the worker in the warehouse. Can be null for workers, which are still active and do not have previous terminations. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

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

### IsActive

Specifies whether the worker is active and can execute new warehouse tasks. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### Name

Name of the worker (multi-language). `Required` `Filter(multi eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  

### Notes

Notes for this WarehouseWorker.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### Person

The definition of the person, when the worker is human worker. null means that the person is unknown or the worker is non-person. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### Warehouse

The warehouse, where the worker works. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Warehouses](Logistics.Wms.Warehouses.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseWorkers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseWorkers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseWorkers?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseWorkers?$top=10>

