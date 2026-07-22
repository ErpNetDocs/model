# Table Saft_Profile_Valuation_Type_By_Valuation_Models


## Entity

Entity: [Regulatory.Saft.ProfileValuationTypeByValuationModels](~/entities/Regulatory.Saft.ProfileValuationTypeByValuationModels.md)

Maps the SAF-T valuation type by Assets Valuation Model for a selected SAF-T profile. Entity: Saft_Profile_Valuation_Type_By_Valuation_Models (Introduced in version 27.1.0.84)

## Owner Tables Hierarchy

* [Saft_Profiles](Saft_Profiles.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Notes](#notes)|`nvarchar(max)` |Additional information or comments about the mapping|
|[Profile_Id](#profile_id)|`uniqueidentifier` |The SAF-T profile this mapping belongs to.|
|[Profile_Valuation_Type_By_Valuation_Model_Id](#profile_valuation_type_by_valuation_model_id)|`uniqueidentifier` `PK`|Unique identifier of the record (GUID).|
|[Row_Version](#row_version)|`timestamp` ||
|[Valuation_Model_Id](#valuation_model_id)|`uniqueidentifier` |The ERP.net Valuation Model for which the SAF-T assets valuation type is defined|
|[Valuation_Type_Code_Entry_Id](#valuation_type_code_entry_id)|`uniqueidentifier` |The SAF-T valuation type used for the selected Valuation Model when generating the SAF-T file.|

## Columns

### Notes


Additional information or comments about the mapping

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Notes - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Profile_Id


The SAF-T profile this mapping belongs to.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|1|
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Saft_Profiles](Saft_Profiles.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Profile_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Profile_Valuation_Type_By_Valuation_Model_Id


Unique identifier of the record (GUID).

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

#### Profile_Valuation_Type_By_Valuation_Model_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

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
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Valuation_Model_Id


The ERP.net Valuation Model for which the SAF-T assets valuation type is defined

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Ast_Valuation_Models](Ast_Valuation_Models.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Valuation_Model_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Valuation_Type_Code_Entry_Id


The SAF-T valuation type used for the selected Valuation Model when generating the SAF-T file.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|3|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Reg_Code_Entries](Reg_Code_Entries.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Valuation_Type_Code_Entry_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


