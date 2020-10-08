# Production.Resources.OperationInstructions

Long (full) instructions for performing an operation. The operations point to the instructions and one instruction can be used for different operations. Entity: Prd_Operation_Instructions

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.OperationInstructions.md#Id) | guid |  
| [Description](Production.Resources.OperationInstructions.md#Description) | string (nullable) | Short description or notes for the instructions. [Filter(like)] 
| [Instructions](Production.Resources.OperationInstructions.md#Instructions) | byte[] (nullable) | The operation instructions in OLE format. 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  

### Description

> Short description or notes for the instructions. [Filter(like)]

_Type_: **string (nullable)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### Instructions

> The operation instructions in OLE format.

_Type_: **byte[] (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  



## Business Rules

[!list erp.entity=Production.Resources.OperationInstructions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Production.Resources.OperationInstructions erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Production.Resources.OperationInstructions erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Production_Resources_OperationInstructions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Production_Resources_OperationInstructions?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Prd_Operation_Instructions?$top=10>
