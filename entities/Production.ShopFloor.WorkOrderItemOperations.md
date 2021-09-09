---
uid: Production.ShopFloor.WorkOrderItemOperations
---
# Production.ShopFloor.WorkOrderItemOperations Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

The operations that are performed to produce the product. Entity: Prd_Work_Order_Item_Operations

## Default Visualization
Default Display Text Format:  
_{WorkOrderItem.LineOrd} : {WorkOrderItem.WorkOrder.DocumentNo} {WorkOrderItem.WorkOrder.DocumentType.TypeName:T}_  
Default Search Member:  
_WorkOrderItem.LineOrd_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActualEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualenddatetime) | datetime __nullable__ | The date/time when the operation has completed. null means that the operation is not completed. 
| [ActualStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualstartdatetime) | datetime __nullable__ | The date/time when the operation has started. null means that the has not started yet. 
| [Id](Production.ShopFloor.WorkOrderItemOperations.md#id) | guid |  
| [LineOrd](Production.ShopFloor.WorkOrderItemOperations.md#lineord) | int32 | Order of the line within the work order routing. `Required` `Filter(eq;like)` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting. 
| [MoveTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes. `Required` `Default(0)` 
| [Notes](Production.ShopFloor.WorkOrderItemOperations.md#notes) | string (254) __nullable__ | Notes for this WorkOrderItemOperation. 
| [OperationDescription](Production.ShopFloor.WorkOrderItemOperations.md#operationdescription) | string (max) __nullable__ | The short description of the operation. 
| [RunTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#runtimeminutes) | int32 | Time for production of one lot of the produced item in minutes. `Required` `Default(0)` 
| [ScheduledEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledenddatetime) | datetime __nullable__ | The date/time when the operation is scheduled to complete. null means that there is still no plan when the operation will finish (for new orders only). 
| [ScheduledStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledstartdatetime) | datetime __nullable__ | The date/time when the operation is planned to start. null means that there is still no plan when to start the operaion (only for new work orders). 
| [ScrapRate](Production.ShopFloor.WorkOrderItemOperations.md#scraprate) | decimal (7, 6) | Projected scrap rate of the operation. `Required` `Default(0)` 
| [SetupTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment in minutes. `Required` `Default(0)` 
| [Tooling](Production.ShopFloor.WorkOrderItemOperations.md#tooling) | string (max) __nullable__ | The tools needed for the routing step. 
| [UseQuantity](Production.ShopFloor.WorkOrderItemOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the resource, that should be allocated for the operation. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Operation](Production.ShopFloor.WorkOrderItemOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | The performed operation. `Filter(multi eq)` |
| [WorkgroupResource](Production.ShopFloor.WorkOrderItemOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The resource that will be used for the operation. null means that no resource will be locked for the operation. `Required` `Filter(multi eq)` |
| [WorkOrderItem](Production.ShopFloor.WorkOrderItemOperations.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item, containing the line. `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Load | [Load](Production.Resources.Load.md) | List of `Load`(Production.Resources.Load.md) child objects, based on the `Production.Resources.Load.WorkOrderItemOperation`(Production.Resources.Load.md#workorderitemoperation) back reference 


## Attribute Details

### ActualEndDateTime

The date/time when the operation has completed. null means that the operation is not completed.

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ActualStartDateTime

The date/time when the operation has started. null means that the has not started yet.

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### LineOrd

Order of the line within the work order routing. `Required` `Filter(eq;like)`

_Type_: **int32**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

_Back-End Default Expression:_  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting.

_Type_: **int32 __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Notes

Notes for this WorkOrderItemOperation.

_Type_: **string (254) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  

### OperationDescription

The short description of the operation.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

_Front-End Recalc Expressions:_  
`obj.Operation.Name`
### RunTimeMinutes

Time for production of one lot of the produced item in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### ScheduledEndDateTime

The date/time when the operation is scheduled to complete. null means that there is still no plan when the operation will finish (for new orders only).

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ScheduledStartDateTime

The date/time when the operation is planned to start. null means that there is still no plan when to start the operaion (only for new work orders).

_Type_: **datetime __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ScrapRate

Projected scrap rate of the operation. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### SetupTimeMinutes

Time needed to setup the equipment in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  

### Tooling

The tools needed for the routing step.

_Type_: **string (max) __nullable__**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  

### UseQuantity

Quantity of the resource, that should be allocated for the operation. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  

### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  


## Reference Details

### Operation

The performed operation. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Supported Filters_: **Equals, EqualsIn**  

### WorkgroupResource

The resource that will be used for the operation. null means that no resource will be locked for the operation. `Required` `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### WorkOrderItem

The work order item, containing the line. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  



## Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemOperations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemOperations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Production_ShopFloor_WorkOrderItemOperations?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_WorkOrderItemOperations?$top=10>

