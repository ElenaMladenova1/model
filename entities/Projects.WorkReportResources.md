---
uid: Projects.WorkReportResources
---
# Projects.WorkReportResources Entity

**Namespace:** [Projects](Projects.md)  

Each record contains usage of resource, reported by the related Work Report. Entity: Prj_Work_Report_Resources

## Default Visualization
Default Display Text Format:  
_{WorkReport.EntityName}_  
Default Search Members:  
_WorkReport.EntityName_  
Name Data Member:  
_WorkReport.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.WorkReports](Projects.WorkReports.md)  
Aggregate Root:  
[Projects.WorkReports](Projects.WorkReports.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActualEndTime](Projects.WorkReportResources.md#actualendtime) | datetime __nullable__ | Optionally, specifies the actual date and time when the resource usage ended. `Filter(eq;like)` 
| [ActualStartTime](Projects.WorkReportResources.md#actualstarttime) | datetime __nullable__ | Optionally, specifies the actual date and time when the resource usage began. `Filter(eq;like)` 
| [DisplayText](Projects.WorkReportResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.WorkReportResources.md#id) | guid |  
| [ObjectVersion](Projects.WorkReportResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TotalResourceUsageHours](Projects.WorkReportResources.md#totalresourceusagehours) | decimal (18, 2) | The total number of resource-hours, which are actually consumed. Equals to the duration of the task, multiplied by the average resource usage. `Required` `Default(0)` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTask](Projects.WorkReportResources.md#projecttask) | [ProjectTasks](Projects.ProjectTasks.md) | The project task for which the work is reported. `Required` `Filter(multi eq)` |
| [Resource](Projects.WorkReportResources.md#resource) | [Resources](General.Resources.Resources.md) | The resource, for which usage is reported. `Required` `Filter(multi eq)` |
| [ResourceInstance](Projects.WorkReportResources.md#resourceinstance) | [ResourceInstances](General.Resources.ResourceInstances.md) (nullable) | The concrete resource instance used. null when no concrete resource was used or there is no data whether concrete resource was used. `Filter(multi eq;like)` |
| [WorkReport](Projects.WorkReportResources.md#workreport) | [WorkReports](Projects.WorkReports.md) | The <see cref="WorkReport"/> to which this WorkReportResource belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ActualEndTime

Optionally, specifies the actual date and time when the resource usage ended. `Filter(eq;like)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### ActualStartTime

Optionally, specifies the actual date and time when the resource usage began. `Filter(eq;like)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### TotalResourceUsageHours

The total number of resource-hours, which are actually consumed. Equals to the duration of the task, multiplied by the average resource usage. `Required` `Default(0)` `Filter(eq;like)`

_Type_: **decimal (18, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### ProjectTask

The project task for which the work is reported. `Required` `Filter(multi eq)`

_Type_: **[ProjectTasks](Projects.ProjectTasks.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

_Back-End Default Expression:_  
`obj.WorkReport.ProjectTask`

_Front-End Recalc Expressions:_  
`obj.WorkReport.ProjectTask`
### Resource

The resource, for which usage is reported. `Required` `Filter(multi eq)`

_Type_: **[Resources](General.Resources.Resources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### ResourceInstance

The concrete resource instance used. null when no concrete resource was used or there is no data whether concrete resource was used. `Filter(multi eq;like)`

_Type_: **[ResourceInstances](General.Resources.ResourceInstances.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.ResourceInstance != null) AndAlso ( obj.ResourceInstance.Resource != obj.Resource)), null, obj.ResourceInstance)`
### WorkReport

The <see cref="WorkReport"/> to which this WorkReportResource belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkReports](Projects.WorkReports.md)**  
_Category_: **System**  
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

[!list limit=1000 erp.entity=Projects.WorkReportResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.WorkReportResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_WorkReportResources?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_WorkReportResources?$top=10>

