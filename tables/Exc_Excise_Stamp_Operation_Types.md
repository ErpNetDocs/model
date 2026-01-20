# Table Exc_Excise_Stamp_Operation_Types


## Entity

Entity: [Regulatory.Excise.ExciseStampOperationTypes](~/entities/Regulatory.Excise.ExciseStampOperationTypes.md)

Specifies the type of the Excise Stamp operation. Entity: Exc_Excise_Stamp_Operation_Types (Introduced in version 22.1.5.85)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Box_1_Effect](#box_1_effect)|`char(1)` Allowed: `N`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.|
|[Box_2_Effect](#box_2_effect)|`char(1)` Allowed: `N`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.|
|[Box_3_Effect](#box_3_effect)|`char(1)` Allowed: `N`, `P`, `M`|Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.|
|[Code](#code)|`nvarchar(32)` ||
|[Excise_Stamp_Operation_Type_Id](#excise_stamp_operation_type_id)|`uniqueidentifier` `PK`||
|[Is_Whole_Lot](#is_whole_lot)|`bit` |Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied.|
|[Name](#name)|`nvarchar(254)` `ML`|Name of operation (multi-language string).|
|[Require_Product](#require_product)|`bit` |Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line.|
|[Row_Version](#row_version)|`timestamp` ||
|[Track_Sequence](#track_sequence)|`bit` |Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved.|

## Columns

### Box_1_Effect


Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

| Property | Value |
| - | - |
|Allowed Values|`N`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|N|
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
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Box_2_Effect


Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

| Property | Value |
| - | - |
|Allowed Values|`N`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|N|
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
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Box_3_Effect


Specifies how the operation changes the Excise Stamp availability in the correspondent Box. The boxes are used to report the availability of excise stamps in the relevant locations according to the requirements of the customs administration.

| Property | Value |
| - | - |
|Allowed Values|`N`, `P`, `M`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|N|
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
|Type|char(1)|
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
|Sortable|yes|
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
|GreaterThanOrLessThan|None|no|yes|

### Is_Whole_Lot


Specifies for this Excise Stamp Operation Type, that when selecting a Excise Stamp Lot within the Excise Stamp Operation line, the entire quantity from the chosen Excise Stamp Lot is copied.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|7|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Is_Whole_Lot - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Name


Name of operation (multi-language string).

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
|Type|nvarchar(254) (MultiLanguage)|
|UI Memo Editor|yes|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Require_Product


Specifies whether for this operation type, the Product field is mandatory in the Excise Stamp Operation line.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|9|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Require_Product - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

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
|Order|6|
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

### Track_Sequence


Checks for this Excise Stamp Operation Type, when entering numbers, the sequence of previously entered numbers is preserved.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|8|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Track_Sequence - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|


