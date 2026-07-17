# Table Saft_Profile_Asset_Transaction_Type_By_Operation_Types


## Entity

Entity: [Regulatory.Saft.ProfileAssetTransactionTypeByOperationTypes](~/entities/Regulatory.Saft.ProfileAssetTransactionTypeByOperationTypes.md)

Maps SAF-T AssetTransactionType for asset transaction lines by operation type and document type. Entity: Saft_Profile_Asset_Transaction_Type_By_Operation_Types (Introduced in version 27.1.0.77)

## Owner Tables Hierarchy

* [Saft_Profiles](Saft_Profiles.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Asset_Transaction_Type_Code_Entry_Id](#asset_transaction_type_code_entry_id)|`uniqueidentifier` |The SAF-T asset transaction type output during SAF-T generation when the mapping criteria are met.|
|[Document_Type_Id](#document_type_id)|`uniqueidentifier` |The ERP.net document type under which this mapping rule should apply. When empty, the rule applies to all document types for the given operation type.|
|[Id](#id)|`uniqueidentifier` `PK`|Unique identifier of the mapping record.|
|[Notes](#notes)|`nvarchar(max)` |Additional information or comments about the mapping.|
|[Operation_Type](#operation_type)|`nvarchar(3)` |The ERP.net operation type of the asset transaction line for which the SAF-T AssetTransactionType is determined.|
|[Profile_Id](#profile_id)|`uniqueidentifier` |The SAF-T profile this mapping belongs to.|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Asset_Transaction_Type_Code_Entry_Id


The SAF-T asset transaction type output during SAF-T generation when the mapping criteria are met.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|4|
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

#### Asset_Transaction_Type_Code_Entry_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Document_Type_Id


The ERP.net document type under which this mapping rule should apply. When empty, the rule applies to all document types for the given operation type.

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
|Referenced Table|[Gen_Document_Types](Gen_Document_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Document_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Id


Unique identifier of the mapping record.

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

#### Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Notes


Additional information or comments about the mapping.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Notes - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Operation_Type


The ERP.net operation type of the asset transaction line for which the SAF-T AssetTransactionType is determined.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|ADJ|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|nvarchar(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Operation_Type - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

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


