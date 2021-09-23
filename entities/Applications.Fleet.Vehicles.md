---
uid: Applications.Fleet.Vehicles
---
# Applications.Fleet.Vehicles Entity

**Namespace:** [Applications.Fleet](Applications.Fleet.md)  

Contains vehicle definitions. Entity: Fleet_Vehicles

## Default Visualization
Default Display Text Format:  
_{EngineIdentificationNumber}_  
Default Search Member:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Fleet.Vehicles](Applications.Fleet.Vehicles.md)  
  * [Applications.Fleet.VehicleEquipment](Applications.Fleet.VehicleEquipment.md)  
  * [Logistics.Shipment.TransportationVehicles](Logistics.Shipment.TransportationVehicles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActiveFrom](Applications.Fleet.Vehicles.md#activefrom) | datetime __nullable__ | The date and time, when the vehicle has been purchased or started to be managed. Null when the date and time are unknown. `Introduced in version 18.2` 
| [ActiveTill](Applications.Fleet.Vehicles.md#activetill) | datetime __nullable__ | The date and time, when the vehicle has been sold or has stopped being managed. Null when the date and time are unknown. `Introduced in version 18.2` 
| [AuthorityMaximum<br />LadenMassKg](Applications.Fleet.Vehicles.md#authoritymaximumladenmasskg) | int32 __nullable__ | Maximum permissible laden mass, as determined by the registration authority. 
| [CrewCount](Applications.Fleet.Vehicles.md#crewcount) | int32 __nullable__ | Crew members count. For road vehicles = 1; for trailers, coaches and wagons =0; air and water vehicles may have higher counts. `Default(1)` `Filter(eq;ge;le)` 
| [EngineIdentificationNumber](Applications.Fleet.Vehicles.md#engineidentificationnumber) | string (20) __nullable__ | Engine identification number. `Filter(eq;like)` 
| [EnginePowerhp](Applications.Fleet.Vehicles.md#enginepowerhp) | int32 __nullable__ | Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)` 
| [EngineSizecc](Applications.Fleet.Vehicles.md#enginesizecc) | int32 __nullable__ | Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)` 
| [FuelCapacity](Applications.Fleet.Vehicles.md#fuelcapacity) | int32 __nullable__ | Maximum fuel capacity of the engine or the battery in the fuel measurement unit. 
| [FuelCompsumption](Applications.Fleet.Vehicles.md#fuelcompsumption) | decimal (7, 1) __nullable__ | Average fuel consumption in the fuel measurement unit for 1 operational unit. 
| [FuelType](Applications.Fleet.Vehicles.md#fueltype) | string (64) __nullable__ | Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)` 
| [Id](Applications.Fleet.Vehicles.md#id) | guid |  
| [IsActive](Applications.Fleet.Vehicles.md#isactive) | boolean | True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Introduced in version 18.2` 
| [IssuingAuthority](Applications.Fleet.Vehicles.md#issuingauthority) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)` 
| [Make](Applications.Fleet.Vehicles.md#make) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)` 
| [ManufactureYear](Applications.Fleet.Vehicles.md#manufactureyear) | int32 __nullable__ | The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)` 
| [MaximumSpeedKmH](Applications.Fleet.Vehicles.md#maximumspeedkmh) | int32 __nullable__ | Maximum speed in km/h. 
| [Model](Applications.Fleet.Vehicles.md#model) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The model of the vehicle. `Filter(eq;like)` 
| [Notes](Applications.Fleet.Vehicles.md#notes) | string (max) __nullable__ | Notes for this Vehicle. 
| [PrimaryColor](Applications.Fleet.Vehicles.md#primarycolor) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | The primary color of the vehicle. null means that the value is unknown or not applicable. `Filter(eq;like)` 
| [SeatingPlacesCount](Applications.Fleet.Vehicles.md#seatingplacescount) | int32 __nullable__ | Number of seating places, excluding driver. `Filter(eq;ge;le)` 
| [StandingPlacesCount](Applications.Fleet.Vehicles.md#standingplacescount) | int32 __nullable__ | Number of standing places, if applicable. 
| [TechnicalMaximum<br />LadenMassKg](Applications.Fleet.Vehicles.md#technicalmaximumladenmasskg) | int32 __nullable__ | Maximum technically permissible laden mass in kg. 
| [TrainsetMaximumLadenMassKg](Applications.Fleet.Vehicles.md#trainsetmaximumladenmasskg) | int32 __nullable__ | Maximum permissible laden mass of a whole trainset, including the vehicle. 
| [VehicleIdentification<br />Number](Applications.Fleet.Vehicles.md#vehicleidentificationnumber) | string (20) __nullable__ | VIN, aka Chassis number. `Filter(eq;like)` 
| [VehicleMassKg](Applications.Fleet.Vehicles.md#vehiclemasskg) | int32 __nullable__ | Vehicle own mass in kg. 
| [VehicleRegistrationNumber](Applications.Fleet.Vehicles.md#vehicleregistrationnumber) | string (16) | The registration plate number. Can be numeric or alphanumeric code. It should be unique within the Issuing_Authority. `Required` `Filter(eq;like)` 
| [VehicleType](Applications.Fleet.Vehicles.md#vehicletype) | [MultilanguageString](../data-types.md#multilanguagestring) __nullable__ | Type of vehicle - e.g. automobile, bus, etc. null means the value is unknown. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [FuelMeasurementUnit](Applications.Fleet.Vehicles.md#fuelmeasurementunit) | [MeasurementUnits](General.MeasurementUnits.md) (nullable) | The measurement unit in which the fuel is measured. E.g. liters for automobiles, Watt-hours for electrics, etc. null means unknown. `Filter(multi eq)` |
| [MaintenanceProfile](Applications.Fleet.Vehicles.md#maintenanceprofile) | [MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) (nullable) | When not null, specifies, that the vehicle should be maintained according to the specified profile. Assigning a profile creates plan assignments for the vehicle. Ultimately, the specific plan assignments are taken into consideration, when planning vehicle maintenance. The profile is only for conveniently assigning multiple plans. `Filter(multi eq)` |
| [OperationalMeasurementUnit](Applications.Fleet.Vehicles.md#operationalmeasurementunit) | [MeasurementUnits](General.MeasurementUnits.md) (nullable) | The measurement unit in which the operation of the vehicle is measured. E.g. km for automobiles, hrs for airplanes, etc. null means that the unit is unknown. `Filter(multi eq)` |
| [OwnerParty](Applications.Fleet.Vehicles.md#ownerparty) | [Parties](General.Contacts.Parties.md) (nullable) | Vehicle owner. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Equipment | [VehicleEquipment](Applications.Fleet.VehicleEquipment.md) | List of `VehicleEquipment`(Applications.Fleet.VehicleEquipment.md) child objects, based on the `Applications.Fleet.VehicleEquipment.Vehicle`(Applications.Fleet.VehicleEquipment.md#vehicle) back reference 
| TransportationVehicles | [TransportationVehicles](Logistics.Shipment.TransportationVehicles.md) | List of `TransportationVehicle`(Logistics.Shipment.TransportationVehicles.md) child objects, based on the `Logistics.Shipment.TransportationVehicle.Vehicle`(Logistics.Shipment.TransportationVehicles.md#vehicle) back reference 


## Attribute Details

### ActiveFrom

The date and time, when the vehicle has been purchased or started to be managed. Null when the date and time are unknown. `Introduced in version 18.2`

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ActiveTill

The date and time, when the vehicle has been sold or has stopped being managed. Null when the date and time are unknown. `Introduced in version 18.2`

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### AuthorityMaximumLadenMassKg

Maximum permissible laden mass, as determined by the registration authority.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### CrewCount

Crew members count. For road vehicles = 1; for trailers, coaches and wagons =0; air and water vehicles may have higher counts. `Default(1)` `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  

### EngineIdentificationNumber

Engine identification number. `Filter(eq;like)`

_Type_: **string (20) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  

### EnginePowerhp

Engine output power in horse power. null means that the value is unknown or not applicable for this type of engine. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### EngineSizecc

Engine size in cubic centimeters (cm3). null means that the value is unknown or not applicable for this type of engine (e.g. electric motors). `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### FuelCapacity

Maximum fuel capacity of the engine or the battery in the fuel measurement unit.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### FuelCompsumption

Average fuel consumption in the fuel measurement unit for 1 operational unit.

_Type_: **decimal (7, 1) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### FuelType

Fuel type of the engine or the power source of the engine (Multilanguage) - e.g. diesel, benzine, electric, etc. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsActive

True if the vehicle is still owned and managed by the enterprise. `Required` `Default(true)` `Introduced in version 18.2`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  

### IssuingAuthority

The country or state issuing the registration number. null (not recommended) means that the authority is unknown or not applicable. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Make

The name of the manufacturer of the vehicle. null means that the value is unknown. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### ManufactureYear

The year when the vehicle was manufactured or first registered - whichever is known. null means that the value is unknown. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### MaximumSpeedKmH

Maximum speed in km/h.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Model

The model of the vehicle. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### Notes

Notes for this Vehicle.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### PrimaryColor

The primary color of the vehicle. null means that the value is unknown or not applicable. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### SeatingPlacesCount

Number of seating places, excluding driver. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### StandingPlacesCount

Number of standing places, if applicable.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TechnicalMaximumLadenMassKg

Maximum technically permissible laden mass in kg.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### TrainsetMaximumLadenMassKg

Maximum permissible laden mass of a whole trainset, including the vehicle.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### VehicleIdentificationNumber

VIN, aka Chassis number. `Filter(eq;like)`

_Type_: **string (20) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **20**  

### VehicleMassKg

Vehicle own mass in kg.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### VehicleRegistrationNumber

The registration plate number. Can be numeric or alphanumeric code. It should be unique within the Issuing_Authority. `Required` `Filter(eq;like)`

_Type_: **string (16)**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  

### VehicleType

Type of vehicle - e.g. automobile, bus, etc. null means the value is unknown. `Filter(eq;like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring) __nullable__**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  


## Reference Details

### FuelMeasurementUnit

The measurement unit in which the fuel is measured. E.g. liters for automobiles, Watt-hours for electrics, etc. null means unknown. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### MaintenanceProfile

When not null, specifies, that the vehicle should be maintained according to the specified profile. Assigning a profile creates plan assignments for the vehicle. Ultimately, the specific plan assignments are taken into consideration, when planning vehicle maintenance. The profile is only for conveniently assigning multiple plans. `Filter(multi eq)`

_Type_: **[MaintenanceProfiles](Applications.Fleet.MaintenanceProfiles.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### OperationalMeasurementUnit

The measurement unit in which the operation of the vehicle is measured. E.g. km for automobiles, hrs for airplanes, etc. null means that the unit is unknown. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.MeasurementUnits.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### OwnerParty

Vehicle owner. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.Vehicles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Fleet.Vehicles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Applications_Fleet_Vehicles?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Applications_Fleet_Vehicles?$top=10>

