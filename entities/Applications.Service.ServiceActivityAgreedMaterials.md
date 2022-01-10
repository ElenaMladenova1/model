---
uid: Applications.Service.ServiceActivityAgreedMaterials
---
# Applications.Service.ServiceActivityAgreedMaterials Entity

**Namespace:** [Applications.Service](Applications.Service.md)  

Contains the materials, which were agreed for this service activity (repair), before its starting. Entity: Srv_Service_Activity_Agreed_Materials

## Default Visualization
Default Display Text Format:  
_{ServiceActivityMaterial.ServiceActivity.EntityName}_  
Default Search Members:  
_ServiceActivityMaterial.ServiceActivity.EntityName_  
Name Data Member:  
_ServiceActivityMaterial.ServiceActivity.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md)  
Aggregate Root:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AgreedQuantity](Applications.Service.ServiceActivityAgreedMaterials.md#agreedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity from the service agreement material line that is accounted for this service activity material line. `Unit: ServiceAgreementMaterial.QuantityUnit` `Required` `Default(0)` `ReadOnly` 
| [DisplayText](Applications.Service.ServiceActivityAgreedMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Service.ServiceActivityAgreedMaterials.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceActivityAgreedMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ServiceActivityMaterial](Applications.Service.ServiceActivityAgreedMaterials.md#serviceactivitymaterial) | [ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md) | The <see cref="ServiceActivity<br />Material"/> to which this ServiceActivity<br />AgreedMaterial belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [ServiceAgreementMaterial](Applications.Service.ServiceActivityAgreedMaterials.md#serviceagreementmaterial) | [ServiceAgreementMaterials](Applications.Service.ServiceAgreementMaterials.md) | Service agreement material line that records the paid or agreed in advance material. `Required` `Filter(multi eq)` `ReadOnly` |


## Attribute Details

### AgreedQuantity

Quantity from the service agreement material line that is accounted for this service activity material line. `Unit: ServiceAgreementMaterial.QuantityUnit` `Required` `Default(0)` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

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

### ServiceActivityMaterial

The <see cref="ServiceActivityMaterial"/> to which this ServiceActivityAgreedMaterial belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  

### ServiceAgreementMaterial

Service agreement material line that records the paid or agreed in advance material. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[ServiceAgreementMaterials](Applications.Service.ServiceAgreementMaterials.md)**  
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

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityAgreedMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityAgreedMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Service_ServiceActivityAgreedMaterials?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceActivityAgreedMaterials?$top=10>

