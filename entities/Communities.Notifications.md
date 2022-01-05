---
uid: Communities.Notifications
---
# Communities.Notifications Entity

**Namespace:** [Communities](Communities.md)  

A single notification of a user. Entity: Cmm_Notifications (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{Id}: {ObjectVersion}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Communities.Notifications](Communities.Notifications.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Communities.Notifications.md#creationtimeutc) | datetime | The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly` 
| [Id](Communities.Notifications.md#id) | guid |  
| [IsRead](Communities.Notifications.md#isread) | boolean | Specifies whether the user has read the notification. If the system changes the notification after first reading, the flag is reset to unread again. `Required` `Default(false)` `Filter(eq)` 
| [NotificationClass](Communities.Notifications.md#notificationclass) | string (64) | The class of the notification from a predefined list of system classes. `Required` `Filter(multi eq)` 
| [ObjectVersion](Communities.Notifications.md#objectversion) | int32 |  
| [Subject](Communities.Notifications.md#subject) | string (256) __nullable__ | The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DataObject](Communities.Notifications.md#dataobject) | [ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable) | The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)` |
| [User](Communities.Notifications.md#user) | [Users](Systems.Security.Users.md) | The user, who is notified. `Required` `Filter(multi eq)` |


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC), when the notification was created. `Required` `Default(NowUtc)` `Filter(ge;le)` `ORD` `ReadOnly`

_Type_: **datetime**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Default Value_: **CurrentDateTimeUtc**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsRead

Specifies whether the user has read the notification. If the system changes the notification after first reading, the flag is reset to unread again. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### NotificationClass

The class of the notification from a predefined list of system classes. `Required` `Filter(multi eq)`

_Type_: **string (64)**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Subject

The short subject of the notification (in the Default Culture of the user). `Filter(eq;like)`

_Type_: **string (256) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  


## Reference Details

### DataObject

The data object about which the notification is created. Null means that the notification is not about any specific data object. `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### User

The user, who is notified. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  


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

[!list limit=1000 erp.entity=Communities.Notifications erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Communities.Notifications erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Communities_Notifications?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Communities_Notifications?$top=10>

