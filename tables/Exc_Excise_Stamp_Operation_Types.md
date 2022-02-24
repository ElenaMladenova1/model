# Table Exc_Excise_Stamp_Operation_Types


## Entity

Entity: [Finance.Excise.ExciseStampOperationTypes](~/entities/Finance.Excise.ExciseStampOperationTypes.md)

Specifies the type of the Excise Stamp operation. Entity: Exc_Excise_Stamp_Operation_Types (Introduced in version 22.1.5.85)

## Summary

| Name | Type | Description |
| - | - | --- |
|[__Object_Version](#__object_version)|`int` ||
|[Box_1_Effect](#box_1_effect)|`nvarchar(1)` Allowed: `Z`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.|
|[Box_2_Effect](#box_2_effect)|`nvarchar(1)` Allowed: `Z`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.|
|[Box_3_Effect](#box_3_effect)|`nvarchar(1)` Allowed: `Z`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.|
|[Code](#code)|`nvarchar(32)` ||
|[Excise_Stamp_Operation_Type_Id](#excise_stamp_operation_type_id)|`uniqueidentifier` `PK`||
|[Name](#name)|`nvarchar(254)` |Multi-language string.|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### __Object_Version

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|int (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Box_1_Effect


Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.

| Property | Value |
| - | - |
|Allowed Values|`Z`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|Z|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|3|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Box_2_Effect


Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.

| Property | Value |
| - | - |
|Allowed Values|`Z`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|Z|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|4|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Box_3_Effect


Specifies how the operation changes the Excise Stamp availability of the correspondent Box. The boxes are used for availability reporting in reported locations according to the requirements of the state administration.

| Property | Value |
| - | - |
|Allowed Values|`Z`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|Z|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
|Order|5|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Code

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|32|
|Order|1|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|nvarchar(32)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Code - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Excise_Stamp_Operation_Type_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|0|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|yes (order: 1)|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Excise_Stamp_Operation_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Name


Multi-language string.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Row_Version

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|


