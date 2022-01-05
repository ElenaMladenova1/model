---
uid: Logistics.Shipment.TransportationExecutionLines
---
# Logistics.Shipment.TransportationExecutionLines Entity

**Namespace:** [Logistics.Shipment](Logistics.Shipment.md)  

Contains details of executions of transportation order lines. Entity: Log_Transportation_Execution_Lines (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {TransportationExecution.DocumentNo} {TransportationExecution.DocumentType.TypeName:T}_  
Default Search Members:  
_TransportationExecution.DocumentNo_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)  
Aggregate Root:  
[Logistics.Shipment.TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExecutionDate](Logistics.Shipment.TransportationExecutionLines.md#executiondate) | date | The date when the operation was executed. `Required` 
| [ExecutionTime](Logistics.Shipment.TransportationExecutionLines.md#executiontime) | time | The time when the operation was executed. `Required` 
| [Id](Logistics.Shipment.TransportationExecutionLines.md#id) | guid |  
| [LineNo](Logistics.Shipment.TransportationExecutionLines.md#lineno) | int32 | Consecutive line number within this execution. `Required` 
| [Notes](Logistics.Shipment.TransportationExecutionLines.md#notes) | string (max) __nullable__ | Notes for this Transportation<br />ExecutionLine. 
| [ObjectVersion](Logistics.Shipment.TransportationExecutionLines.md#objectversion) | int32 |  
| [OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype) | [OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype) | The type of operation being executed. L=Loading; U=Unloading; O=Other. `Required` 
| [PalletNumber](Logistics.Shipment.TransportationExecutionLines.md#palletnumber) | string (32) __nullable__ | Pallet number, when applicable. null when unknown or not applicable. 
| [PalletsCount](Logistics.Shipment.TransportationExecutionLines.md#palletscount) | int32 __nullable__ | Number of pallets affected by this operation. null when unknown or N/A. 
| [VolumeCbm](Logistics.Shipment.TransportationExecutionLines.md#volumecbm) | int32 __nullable__ | Cargo volume in cubic meters, affected by this operation. null when unknown or N/A. 
| [WeightKg](Logistics.Shipment.TransportationExecutionLines.md#weightkg) | int32 __nullable__ | Cargo weight in kg, affected by this operation. null when unknown or N/A. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Shipment.TransportationExecutionLines.md#document) | [TransportationExecutions](Logistics.Shipment.TransportationExecutions.md) | The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` |
| [ExecutionOfTransportation<br />OrderLine](Logistics.Shipment.TransportationExecutionLines.md#executionoftransportationorderline) | [TransportationOrderLines](Logistics.Shipment.TransportationOrderLines.md) | The transportation order line, which is executed. `Required` `Filter(multi eq)` |
| [GeoPoint](Logistics.Shipment.TransportationExecutionLines.md#geopoint) | [GeoPoints](General.Geography.GeoPoints.md) | The geographic point, where the operation is executed. `Required` `Filter(multi eq)` |
| [TransportationExecution](Logistics.Shipment.TransportationExecutionLines.md#transportationexecution) | [TransportationExecutions](Logistics.Shipment.TransportationExecutions.md) | The <see cref="Transportation<br />Execution"/> to which this Transportation<br />ExecutionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ExecutionDate

The date when the operation was executed. `Required`

_Type_: **date**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`obj.TransportationExecution.ExecutionDate`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.ExecutionDate`
### ExecutionTime

The time when the operation was executed. `Required`

_Type_: **time**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`obj.TransportationExecution.ExecutionTime`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.ExecutionTime`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineNo

Consecutive line number within this execution. `Required`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.TransportationExecution.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this TransportationExecutionLine.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### ObjectVersion

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### OperationType

The type of operation being executed. L=Loading; U=Unloading; O=Other. `Required`

_Type_: **[OperationType](Logistics.Shipment.TransportationExecutionLines.md#operationtype)**  
Allowed values for the `OperationType`(Logistics.Shipment.TransportationExecutionLines.md#operationtype) data attribute  
_Allowed Values (Logistics.Shipment.TransportationExecutionLinesRepository.OperationType Enum Members)_  

| Value | Description |
| ---- | --- |
| Loading | Loading value. Stored as 'L'. <br /> _Database Value:_ 'L' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Loading' |
| Unloading | Unloading value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Unloading' |
| Other | Other value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### PalletNumber

Pallet number, when applicable. null when unknown or not applicable.

_Type_: **string (32) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  

### PalletsCount

Number of pallets affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### VolumeCbm

Cargo volume in cubic meters, affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### WeightKg

Cargo weight in kg, affected by this operation. null when unknown or N/A.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### Document

The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)`

_Type_: **[TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  

### ExecutionOfTransportationOrderLine

The transportation order line, which is executed. `Required` `Filter(multi eq)`

_Type_: **[TransportationOrderLines](Logistics.Shipment.TransportationOrderLines.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### GeoPoint

The geographic point, where the operation is executed. `Required` `Filter(multi eq)`

_Type_: **[GeoPoints](General.Geography.GeoPoints.md)**  
_Supported Filters_: **Equals, EqualsIn**  

_Back-End Default Expression:_  
`obj.TransportationExecution.GeoPoint`

_Front-End Recalc Expressions:_  
`obj.TransportationExecution.GeoPoint`
### TransportationExecution

The <see cref="TransportationExecution"/> to which this TransportationExecutionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[TransportationExecutions](Logistics.Shipment.TransportationExecutions.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationExecutionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.TransportationExecutionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Shipment_TransportationExecutionLines?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_TransportationExecutionLines?$top=10>

