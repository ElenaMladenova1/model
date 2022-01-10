---
uid: Applications.Fleet.VehicleLocationHistoryRecords
---
# Applications.Fleet.VehicleLocationHistoryRecords Entity

**Namespace:** [Applications.Fleet](Applications.Fleet.md)  

Stores information about vehicle locations. Entity: Fleet_Vehicle_Location_History_Records

## Default Visualization
Default Display Text Format:  
_{Id}: {VehicleId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Fleet.VehicleLocationHistoryRecords](Applications.Fleet.VehicleLocationHistoryRecords.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentSpeedKmH](Applications.Fleet.VehicleLocationHistoryRecords.md#currentspeedkmh) | int32 __nullable__ | The current speed of the vehicle in km/h. null means the speed is unknown. `Introduced in version 19.1` 
| [DisplayText](Applications.Fleet.VehicleLocationHistoryRecords.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Fleet.VehicleLocationHistoryRecords.md#id) | guid |  
| [Latitude](Applications.Fleet.VehicleLocationHistoryRecords.md#latitude) | decimal (10, 7) | Latitude of the vehicle at the specified time. Latitude is the vertical angle from equator to the pole of the point. Positive values denote points north of the equator. The value is in the range `-90, 90`. `Required` 
| [Longitude](Applications.Fleet.VehicleLocationHistoryRecords.md#longitude) | decimal (10, 7) | Longitude of the vehicle at the specified time. Longitude is angle from the prime meridian (in England) in east-west direction. Positive values denote east and negative - west. The value is in the range `-180, 180`. `Required` 
| [ObjectVersion](Applications.Fleet.VehicleLocationHistoryRecords.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Time](Applications.Fleet.VehicleLocationHistoryRecords.md#time) | datetime | The time, for which the location is stored. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Vehicle](Applications.Fleet.VehicleLocationHistoryRecords.md#vehicle) | [Vehicles](Applications.Fleet.Vehicles.md) | The vehicle, whose location is being stored. `Required` `Filter(multi eq)` |


## Attribute Details

### CurrentSpeedKmH

The current speed of the vehicle in km/h. null means the speed is unknown. `Introduced in version 19.1`

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
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

### Latitude

Latitude of the vehicle at the specified time. Latitude is the vertical angle from equator to the pole of the point. Positive values denote points north of the equator. The value is in the range `-90, 90`. `Required`

_Type_: **decimal (10, 7)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Longitude

Longitude of the vehicle at the specified time. Longitude is angle from the prime meridian (in England) in east-west direction. Positive values denote east and negative - west. The value is in the range `-180, 180`. `Required`

_Type_: **decimal (10, 7)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Time

The time, for which the location is stored. `Required`

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Vehicle

The vehicle, whose location is being stored. `Required` `Filter(multi eq)`

_Type_: **[Vehicles](Applications.Fleet.Vehicles.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Applications.Fleet.VehicleLocationHistoryRecords erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.VehicleLocationHistoryRecords erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Fleet_VehicleLocationHistoryRecords?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Fleet_VehicleLocationHistoryRecords?$top=10>

