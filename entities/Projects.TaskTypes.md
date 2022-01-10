---
uid: Projects.TaskTypes
---
# Projects.TaskTypes Entity

**Namespace:** [Projects](Projects.md)  

Represents the different types of tasks, which can be included in the projects. Entity: Prj_Task_Types

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.TaskTypes](Projects.TaskTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Projects.TaskTypes.md#description) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | Multilanguage description of the task type. 
| [DisplayOrder](Projects.TaskTypes.md#displayorder) | int32 | Display order position of the task. Lowest numbers are shown first (on top). `Required` `Default(1)` 
| [DisplayText](Projects.TaskTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Icon](Projects.TaskTypes.md#icon) | byte[] __nullable__ | Icon representing the task type. Preferrably 32x32 pixels. 
| [Id](Projects.TaskTypes.md#id) | guid |  
| [Name](Projects.TaskTypes.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | The multilanguage task type name. `Required` `Filter(multi eq;like)` 
| [ObjectVersion](Projects.TaskTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectType](Projects.TaskTypes.md#projecttype) | [ProjectTypes](Projects.ProjectTypes.md) (nullable) | When not null, specifies that this task type can be used only for projects of the specified type. `Filter(multi eq)` |


## Attribute Details

### Description

Multilanguage description of the task type.

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### DisplayOrder

Display order position of the task. Lowest numbers are shown first (on top). `Required` `Default(1)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Icon

Icon representing the task type. Preferrably 32x32 pixels.

_Type_: **byte[] __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Name

The multilanguage task type name. `Required` `Filter(multi eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  


## Reference Details

### ProjectType

When not null, specifies that this task type can be used only for projects of the specified type. `Filter(multi eq)`

_Type_: **[ProjectTypes](Projects.ProjectTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.TaskTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.TaskTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TaskTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TaskTypes?$top=10>

