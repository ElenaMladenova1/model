---
uid: Finance.Assets.DepreciationMethods
---
# Finance.Assets.DepreciationMethods Entity

**Namespace:** [Finance.Assets](Finance.Assets.md)  

Depreciation methods. Contains both system-defined and user-defined methods. Entity: Ast_Depreciation_Methods

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Assets.DepreciationMethods](Finance.Assets.DepreciationMethods.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | [DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction) | Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table. `Required` `Default("STL")` 
| [DisplayText](Finance.Assets.DepreciationMethods.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Factor](Finance.Assets.DepreciationMethods.md#factor) | decimal (5, 3) | Factor used in factor depreciation function. Factor &lt; 1 means declining depreciation; &gt;1 - increasing. The depreciation is multiplied for each period by the factor. `Required` `Default(1)` 
| [Id](Finance.Assets.DepreciationMethods.md#id) | guid |  
| [IsSystem](Finance.Assets.DepreciationMethods.md#issystem) | boolean | Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [MonthsInAPeriod](Finance.Assets.DepreciationMethods.md#monthsinaperiod) | int32 | Number of equal valued months calculated with single application of the function. `Required` `Default(12)` 
| [Name](Finance.Assets.DepreciationMethods.md#name) | [MultilanguageString](../data-types.md#multilanguagestring) | The name of this DepreciationMethod(Multilanguage string).. `Required` `Filter(like)` 
| [ObjectVersion](Finance.Assets.DepreciationMethods.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | [PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) | Determines when the depreciation starts and when it ends. NM=Next_Month, CM=Current_Month, BD=By_Days. `Required` 
| [StartFromNextMonth](Finance.Assets.DepreciationMethods.md#startfromnextmonth) | boolean | When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month. `Required` `Default(true)` `ReadOnly` 


## Attribute Details

### DepreciationFunction

Basic mathematical depreciation function used to calculate asset depreciation. STL=Straight Line, SYD=Sum of Years Digits, FAC=Depreciation change by factor, TAB=User defined with table. `Required` `Default("STL")`

_Type_: **[DepreciationFunction](Finance.Assets.DepreciationMethods.md#depreciationfunction)**  
Allowed values for the `DepreciationFunction`(Finance.Assets.DepreciationMethods.md#depreciationfunction) data attribute  
_Allowed Values (Finance.Assets.DepreciationMethodsRepository.DepreciationFunction Enum Members)_  

| Value | Description |
| ---- | --- |
| DepreciationChangeByFactor | DepreciationChangeByFactor value. Stored as 'FAC'. <br /> _Database Value:_ 'FAC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DepreciationChangeByFactor' |
| StraightLine | StraightLine value. Stored as 'STL'. <br /> _Database Value:_ 'STL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'StraightLine' |
| SumOfYearsDigits | SumOfYearsDigits value. Stored as 'SYD'. <br /> _Database Value:_ 'SYD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'SumOfYearsDigits' |
| UserDefinedWithTable | UserDefinedWithTable value. Stored as 'TAB'. <br /> _Database Value:_ 'TAB' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'UserDefinedWithTable' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **StraightLine**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Factor

Factor used in factor depreciation function. Factor &lt; 1 means declining depreciation; &gt;1 - increasing. The depreciation is multiplied for each period by the factor. `Required` `Default(1)`

_Type_: **decimal (5, 3)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsSystem

Is_System is True for those depreciation methods that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### MonthsInAPeriod

Number of equal valued months calculated with single application of the function. `Required` `Default(12)`

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **12**  

### Name

The name of this DepreciationMethod(Multilanguage string).. `Required` `Filter(like)`

_Type_: **[MultilanguageString](../data-types.md#multilanguagestring)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### PeriodDeterminationMethod

Determines when the depreciation starts and when it ends. NM=Next_Month, CM=Current_Month, BD=By_Days. `Required`

_Type_: **[PeriodDeterminationMethod](Finance.Assets.DepreciationMethods.md#perioddeterminationmethod)**  
Allowed values for the `PeriodDeterminationMethod`(Finance.Assets.DepreciationMethods.md#perioddeterminationmethod) data attribute  
_Allowed Values (Finance.Assets.DepreciationMethodsRepository.PeriodDeterminationMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| NextMonth | NextMonth value. Stored as 'NM'. <br /> _Database Value:_ 'NM' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NextMonth' |
| CurrentMonth | CurrentMonth value. Stored as 'CM'. <br /> _Database Value:_ 'CM' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CurrentMonth' |
| ByDays | ByDays value. Stored as 'BD'. <br /> _Database Value:_ 'BD' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ByDays' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### StartFromNextMonth

When true, denotes that the depreciation starts from the month, following the month of deployment. When false, the depreciation starts from the same month. `Required` `Default(true)` `ReadOnly`

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  


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

[!list limit=1000 erp.entity=Finance.Assets.DepreciationMethods erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.DepreciationMethods erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Assets_DepreciationMethods?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Assets_DepreciationMethods?$top=10>

