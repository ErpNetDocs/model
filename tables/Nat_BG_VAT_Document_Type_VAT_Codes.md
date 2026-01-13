# Table Nat_BG_VAT_Document_Type_VAT_Codes


## Entity

Entity: [Finance.Vat.BGVATDocumentTypeVATCodes](~/entities/Finance.Vat.BGVATDocumentTypeVATCodes.md)

Contains the VAT codes, which should be used, when reporting VAT for the different document types. Entity: Nat_BG_VAT_Document_Type_VAT_Codes

## Summary

| Name | Type | Description |
| - | - | --- |
|[Cash_Reporting_VAT_Code](#cash_reporting_vat_code)|`char(2)` Allowed: `01`, `02`, `03`, `04`, `05`, `07`, `09`, `11`, `12`, `13`, `23`, `29`, `50`, `81`, `82`, `83`, `84`, `85`, `91`, `92`, `93`, `94`|VAT code, which will be used when Cash Reporting mode is used for the entry. Allowed values are the same as for VAT Code.|
|[Document_Type_Id](#document_type_id)|`uniqueidentifier` |Document type that generates VAT entries.|
|[Document_Type_VAT_Code_Id](#document_type_vat_code_id)|`uniqueidentifier` `PK`|Unique identification of the record.|
|[Row_Version](#row_version)|`timestamp` ||
|[VAT_Code](#vat_code)|`char(2)` Allowed: `01`, `02`, `03`, `04`, `05`, `07`, `09`, `11`, `12`, `13`, `23`, `29`, `50`, `81`, `82`, `83`, `84`, `85`, `91`, `92`, `93`, `94`|VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values.|

## Columns

### Cash_Reporting_VAT_Code


VAT code, which will be used when Cash Reporting mode is used for the entry. Allowed values are the same as for VAT Code.

| Property | Value |
| - | - |
|Allowed Values|`01`, `02`, `03`, `04`, `05`, `07`, `09`, `11`, `12`, `13`, `23`, `29`, `50`, `81`, `82`, `83`, `84`, `85`, `91`, `92`, `93`, `94`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2|
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
|Type|char(2) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Document_Type_Id


Document type that generates VAT entries.

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
|Referenced Table|[Gen_Document_Types](Gen_Document_Types.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Long|
|User Login|no|
|Visible|yes|

#### Document_Type_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Document_Type_VAT_Code_Id


Unique identification of the record.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
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

#### Document_Type_VAT_Code_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
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

### VAT_Code


VAT code to use when creating VAT export files for the specified Document Type. Allowed values is government-regulated list of values.

| Property | Value |
| - | - |
|Allowed Values|`01`, `02`, `03`, `04`, `05`, `07`, `09`, `11`, `12`, `13`, `23`, `29`, `50`, `81`, `82`, `83`, `84`, `85`, `91`, `92`, `93`, `94`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2|
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
|Type|char(2) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Long|
|User Login|no|
|Visible|yes|


