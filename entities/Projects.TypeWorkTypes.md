---
uid: Projects.TypeWorkTypes
---
# Projects.TypeWorkTypes Entity

**Namespace:** [Projects](Projects.md)  

Contains the work types, that can be performed in projects of this project type. Entity: Prj_Type_Work_Types

## Default Visualization
Default Display Text Format:  
_{WorkTypeName}_  
Default Search Members:  
_WorkTypeName_  
Name Data Member:  
_WorkTypeName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.ProjectTypes](Projects.ProjectTypes.md)  
Aggregate Root:  
[Projects.ProjectTypes](Projects.ProjectTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Projects.TypeWorkTypes.md#displaytext) | string |  
| [Id](Projects.TypeWorkTypes.md#id) | guid |  
| [IsActive](Projects.TypeWorkTypes.md#isactive) | boolean | True when the work type is currently active and selectable in new documents. `Required` `Default(true)` `Filter(eq)` 
| [ObjectVersion](Projects.TypeWorkTypes.md#objectversion) | int32 |  
| [WorkTypeName](Projects.TypeWorkTypes.md#worktypename) | string (254) | The name of the work type. `Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BilledWithProduct](Projects.TypeWorkTypes.md#billedwithproduct) | [Products](General.Products.Products.md) (nullable) | The product, which is used for billing purposes for this work type. The price of the product is also used for project budgeting. null means that the work type cannot be billed. `Filter(multi eq)` |
| [ProjectType](Projects.TypeWorkTypes.md#projecttype) | [ProjectTypes](Projects.ProjectTypes.md) | The <see cref="ProjectType"/> to which this TypeWorkType belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsActive

True when the work type is currently active and selectable in new documents. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### WorkTypeName

The name of the work type. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  


## Reference Details

### BilledWithProduct

The product, which is used for billing purposes for this work type. The price of the product is also used for project budgeting. null means that the work type cannot be billed. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### ProjectType

The <see cref="ProjectType"/> to which this TypeWorkType belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProjectTypes](Projects.ProjectTypes.md)**  
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

[!list limit=1000 erp.entity=Projects.TypeWorkTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.TypeWorkTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TypeWorkTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TypeWorkTypes?$top=10>

