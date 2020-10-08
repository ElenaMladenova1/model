# Systems.Bpm.UserBusinessRules

Represents user-defined business rule. Entity: Sys_User_Business_Rules

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.UserBusinessRules.md#Id) | guid |  
| [Icon](Systems.Bpm.UserBusinessRules.md#Icon) | byte[] (nullable) | Visual icon of the rule in .PNG format. 
| [IsActive](Systems.Bpm.UserBusinessRules.md#IsActive) | boolean | Specifies whether the rule is activated. [Required] [Default(false)] [Filter(eq)] 
| [Layer](Systems.Bpm.UserBusinessRules.md#Layer) | [Systems.Bpm.UserBusinessRulesRepository.Layer](Systems.Bpm.UserBusinessRules.md#Layer) | Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both). [Required] [Default("BKE")] [Filter(multi eq)] 
| [Notes](Systems.Bpm.UserBusinessRules.md#Notes) | string (nullable) | Notes for this UserBusinessRule. 
| [RepositoryName](Systems.Bpm.UserBusinessRules.md#RepositoryName) | string | The name of the repository, for which this business rule is defined. [Required] [Filter(eq;like)] 
| [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#ScriptLanguage) | [Systems.Bpm.UserBusinessRulesRepository.ScriptLanguage](Systems.Bpm.UserBusinessRules.md#ScriptLanguage) | The programming language used to define the rule actions. [Required] [Default("Integrated")] 
| [ScriptText](Systems.Bpm.UserBusinessRules.md#ScriptText) | string (nullable) | The program code used to define the rule actions. 
| [Code](Systems.Bpm.UserBusinessRules.md#Code) | string | The unique code of the UserBusinessRule. [Required] [Filter(eq;like)] [ORD] 
| [Name](Systems.Bpm.UserBusinessRules.md#Name) | [MultilanguageString](../data-types/MultilanguageString.md) | The name of this UserBusinessRule. [Required] [Filter(like)] 
| [UserStartable](Systems.Bpm.UserBusinessRules.md#UserStartable) | boolean (nullable) | Specifies, that the rule can be manually started by the user. [Default(false)] [Filter(eq)] 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Actions | [Systems.Bpm.UserBusinessRuleActions](Systems.Bpm.UserBusinessRuleActions.md) | List of [UserBusinessRuleAction](Systems.Bpm.UserBusinessRuleActions.md) child objects, based on the [Systems.Bpm.UserBusinessRuleAction.UserBusinessRule](Systems.Bpm.UserBusinessRuleActions.md#UserBusinessRule) back reference 
| Conditions | [Systems.Bpm.UserBusinessRuleConditions](Systems.Bpm.UserBusinessRuleConditions.md) | List of [UserBusinessRuleCondition](Systems.Bpm.UserBusinessRuleConditions.md) child objects, based on the [Systems.Bpm.UserBusinessRuleCondition.UserBusinessRule](Systems.Bpm.UserBusinessRuleConditions.md#UserBusinessRule) back reference 
| Events | [Systems.Bpm.UserBusinessRuleEvents](Systems.Bpm.UserBusinessRuleEvents.md) | List of [UserBusinessRuleEvent](Systems.Bpm.UserBusinessRuleEvents.md) child objects, based on the [Systems.Bpm.UserBusinessRuleEvent.UserBusinessRule](Systems.Bpm.UserBusinessRuleEvents.md#UserBusinessRule) back reference 


## Attribute Details

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **NewGuid**  

### Icon

> Visual icon of the rule in .PNG format.

_Type_: **byte[] (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### IsActive

> Specifies whether the rule is activated. [Required] [Default(false)] [Filter(eq)]

_Type_: **boolean**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  

### Layer

> Specifies in which layers the rule will be available. The available events and actions depend on the chosen layer.  Allowed values: FTE=Front-End, BKE=BackEnd, COM=Common (both). [Required] [Default("BKE")] [Filter(multi eq)]

_Type_: **[Systems.Bpm.UserBusinessRulesRepository.Layer](Systems.Bpm.UserBusinessRules.md#Layer)**  
Allowed values for the [Layer](Systems.Bpm.UserBusinessRules.md#Layer) data attribute  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| FrontEnd | The rule is registered for front-end applications.. Stored as 'FTE'. <br /> _Database Value:_ 'FTE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'FrontEnd' |
| BackEnd | The rule is registered for server execution.. Stored as 'BKE'. <br /> _Database Value:_ 'BKE' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BackEnd' |
| Common | The rule is registered both for server and client.. Stored as 'COM'. <br /> _Database Value:_ 'COM' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Common' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **BackEnd**  

### Notes

> Notes for this UserBusinessRule.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### RepositoryName

> The name of the repository, for which this business rule is defined. [Required] [Filter(eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  

### ScriptLanguage

> The programming language used to define the rule actions. [Required] [Default("Integrated")]

_Type_: **[Systems.Bpm.UserBusinessRulesRepository.ScriptLanguage](Systems.Bpm.UserBusinessRules.md#ScriptLanguage)**  
Allowed values for the [ScriptLanguage](Systems.Bpm.UserBusinessRules.md#ScriptLanguage) data attribute  
_Allowed Values (Enum Members)_  

| Value | Description |
| ---- | --- |
| Integrated | Integrated value. Stored as 'Integrated'. <br /> _Database Value:_ 'Integrated' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Integrated' |
| CSharp | CSharp value. Stored as 'CSharp'. <br /> _Database Value:_ 'CSharp' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CSharp' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Integrated**  

### ScriptText

> The program code used to define the rule actions.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Code

> The unique code of the UserBusinessRule. [Required] [Filter(eq;like)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  

### Name

> The name of this UserBusinessRule. [Required] [Filter(like)]

_Type_: **[MultilanguageString](../data-types/MultilanguageString.md)**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  

### UserStartable

> Specifies, that the rule can be manually started by the user. [Default(false)] [Filter(eq)]

_Type_: **boolean (nullable)**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  



## Business Rules

[!list erp.entity=Systems.Bpm.UserBusinessRules erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Systems.Bpm.UserBusinessRules erp.type=front-end-business-rule default-text="None"]

## Generations

[!list erp.entity=Systems.Bpm.UserBusinessRules erp.type=generation default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRules?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRules?$top=10>

Table API Query:
<https://demodb.my.erp.net/api/domain/odata/Sys_User_Business_Rules?$top=10>
