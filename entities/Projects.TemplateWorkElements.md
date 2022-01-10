---
uid: Projects.TemplateWorkElements
---
# Projects.TemplateWorkElements Entity

**Namespace:** [Projects](Projects.md)  

Contains project work elements, which shall be copied to projects, based on the specified template. Entity: Prj_Template_Work_Elements

## Default Visualization
Default Display Text Format:  
_{ProjectTemplate.ProjectTemplateName}_  
Default Search Members:  
_ProjectTemplate.ProjectTemplateName_  
Name Data Member:  
_ProjectTemplate.ProjectTemplateName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Templates](Projects.Templates.md)  
Aggregate Root:  
[Projects.Templates](Projects.Templates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Projects.TemplateWorkElements.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.TemplateWorkElements.md#id) | guid |  
| [ObjectVersion](Projects.TemplateWorkElements.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTemplate](Projects.TemplateWorkElements.md#projecttemplate) | [Templates](Projects.Templates.md) | The <see cref="Template"/> to which this TemplateWorkElement belongs. `Required` `Filter(multi eq)` `Owner` |
| [ProjectTypeWorkElement](Projects.TemplateWorkElements.md#projecttypeworkelement) | [TypeWorkElements](Projects.TypeWorkElements.md) | The work element from the project type, which shall be copied as work element in new projects, based on this template. `Required` `Filter(multi eq)` |


## Attribute Details

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


## Reference Details

### ProjectTemplate

The <see cref="Template"/> to which this TemplateWorkElement belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Templates](Projects.Templates.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### ProjectTypeWorkElement

The work element from the project type, which shall be copied as work element in new projects, based on this template. `Required` `Filter(multi eq)`

_Type_: **[TypeWorkElements](Projects.TypeWorkElements.md)**  
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

[!list limit=1000 erp.entity=Projects.TemplateWorkElements erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.TemplateWorkElements erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_TemplateWorkElements?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_TemplateWorkElements?$top=10>

