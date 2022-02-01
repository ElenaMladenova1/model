---
uid: Crm.Marketing.Campaigns
---
# Crm.Marketing.Campaigns Entity

**Namespace:** [Crm.Marketing](Crm.Marketing.md)  

Marketing campaigns. Used to treat target groups with marketing messages, plan budgets and marketing activities. Entity: Crm_Campaigns

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Marketing.Campaigns](Crm.Marketing.Campaigns.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Crm.Marketing.Campaigns.md#description) | string (254) __nullable__ | Campaign description. 
| [DisplayText](Crm.Marketing.Campaigns.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndDate](Crm.Marketing.Campaigns.md#enddate) | datetime __nullable__ | End date of the campaign. null means that the end date is still unknown. 
| [ForecastedCost](Crm.Marketing.Campaigns.md#forecastedcost) | decimal (18, 0) | Forecasted total cost of the campaign. `Required` `Default(0)` 
| [Id](Crm.Marketing.Campaigns.md#id) | guid |  
| [Name](Crm.Marketing.Campaigns.md#name) | string (64) | Short name of the campaign. `Required` `Filter(like)` `ORD` 
| [ObjectVersion](Crm.Marketing.Campaigns.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartDate](Crm.Marketing.Campaigns.md#startdate) | datetime | Starting date of the campaign. `Required` `Default(Today)` 


## Attribute Details

### Description

Campaign description.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### EndDate

End date of the campaign. null means that the end date is still unknown.

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ForecastedCost

Forecasted total cost of the campaign. `Required` `Default(0)`

_Type_: **decimal (18, 0)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### Name

Short name of the campaign. `Required` `Filter(like)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### StartDate

Starting date of the campaign. `Required` `Default(Today)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  


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

[!list limit=1000 erp.entity=Crm.Marketing.Campaigns erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.Campaigns erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Marketing_Campaigns?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Marketing_Campaigns?$top=10>

