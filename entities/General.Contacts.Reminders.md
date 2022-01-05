---
uid: General.Contacts.Reminders
---
# General.Contacts.Reminders Entity

**Namespace:** [General.Contacts](General.Contacts.md)  

Reminders for activities. The reminders are alarms, which can be turned off. Each activity can have multiple reminders. Entity: Cm_Reminders

## Default Visualization
Default Display Text Format:  
_{Activity.EntityName}_  
Default Search Members:  
_Activity.EntityName_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Activities](General.Contacts.Activities.md)  
Aggregate Root:  
[General.Contacts.Activities](General.Contacts.Activities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.Reminders.md#id) | guid |  
| [IsDefault](General.Contacts.Reminders.md#isdefault) | boolean | True when this is the defult reminder for a task. The default reminder is controlled through the task, while non-default reminders are manipulated through separate form. `Required` `Default(false)` `Filter(eq)` 
| [IsDismissed](General.Contacts.Reminders.md#isdismissed) | boolean | When true the reminder was dismissed by the user; the initial value is false. `Required` `Default(false)` `Filter(eq)` 
| [Notes](General.Contacts.Reminders.md#notes) | string (max) __nullable__ | Notes that describe this specific reminder for the task. 
| [ObjectVersion](General.Contacts.Reminders.md#objectversion) | int32 |  
| [ReminderTime](General.Contacts.Reminders.md#remindertime) | datetime | The time when the alarm should snooze to the user. `Required` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](General.Contacts.Reminders.md#activity) | [Activities](General.Contacts.Activities.md) | The activity to which this reminder is attached. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsDefault

True when this is the defult reminder for a task. The default reminder is controlled through the task, while non-default reminders are manipulated through separate form. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### IsDismissed

When true the reminder was dismissed by the user; the initial value is false. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Notes

Notes that describe this specific reminder for the task.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### ReminderTime

The time when the alarm should snooze to the user. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  


## Reference Details

### Activity

The activity to which this reminder is attached. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Activities](General.Contacts.Activities.md)**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  


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

[!list limit=1000 erp.entity=General.Contacts.Reminders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.Reminders erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Contacts_Reminders?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Contacts_Reminders?$top=10>

