---
uid: Projects.Templates
---
# Projects.Templates Entity

**Namespace:** [Projects](Projects.md)  

Contains templates for creating new projects. Entity: Prj_Templates

## Default Visualization
Default Display Text Format:  
_{ProjectTemplateName}_  
Default Search Members:  
_ProjectTemplateName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Templates](Projects.Templates.md)  
  * [Projects.TemplateRisks](Projects.TemplateRisks.md)  
  * [Projects.TemplateWorkElements](Projects.TemplateWorkElements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Templates.md#id) | guid |  
| [Notes](Projects.Templates.md#notes) | string (max) __nullable__ | Notes for this Template. 
| [ObjectVersion](Projects.Templates.md#objectversion) | int32 |  
| [ProjectTemplateName](Projects.Templates.md#projecttemplatename) | string (254) | The name of the project template. `Required` 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Risks | [TemplateRisks](Projects.TemplateRisks.md) | List of `TemplateRisk`(Projects.TemplateRisks.md) child objects, based on the `Projects.TemplateRisk.ProjectTemplate`(Projects.TemplateRisks.md#projecttemplate) back reference 
| WorkElements | [TemplateWorkElements](Projects.TemplateWorkElements.md) | List of `TemplateWorkElement`(Projects.TemplateWorkElements.md) child objects, based on the `Projects.TemplateWorkElement.ProjectTemplate`(Projects.TemplateWorkElements.md#projecttemplate) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Notes

Notes for this Template.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ProjectTemplateName

The name of the project template. `Required`

_Type_: **string (254)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources does not support ordering.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description  
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

[!list limit=1000 erp.entity=Projects.Templates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Templates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_Templates?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_Templates?$top=10>

